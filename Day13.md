# STATIC TYPING QUESTION:
#### [Excercise1](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/tree/main/learning-sprint-1/week3-day2-tasks)
```typescript
//defining the necessary types and interfaces
interface HelloWorldResult {
  message: string;
}

interface BooleanResult {
  booleanValue: boolean;
}

interface ReturnObjResult {
  x: string;
  y: number;
}

type PromiseResult = HelloWorldResult | BooleanResult | ReturnObjResult;

interface PromiseFunctions {
  (): Promise<PromiseResult>;
}

interface PromisesObject {
  [key: string]: PromiseFunctions;
}
//implement the convertToObj function and create the promises object
const sayHelloWorld = new Promise<HelloWorldResult>((resolve) => {
  resolve({ message: "Hello world!" });
});

const checkBoolean = (boolean: boolean) =>
  new Promise<BooleanResult>((resolve, reject) => {
    if (boolean) {
      resolve({ booleanValue: boolean });
    } else {
      reject(`Input is false :(`);
    }
  });

const returnObj = new Promise<ReturnObjResult>((resolve) => {
  resolve({
    x: "meow",
    y: 45,
  });
});

const promisesArray = [sayHelloWorld, () => checkBoolean(true), returnObj];

const convertToObj = (array: Array<PromiseFunctions>): PromisesObject => {
  const obj: PromisesObject = {};

  array.forEach((promiseFunc, index) => {
    const key = `promise${index + 1}`;

    obj[key] = () =>
      new Promise<PromiseResult>((resolve, reject) => {
        promiseFunc()
          .then((result) => resolve(result))
          .catch((error) => reject(error));
      });
  });

  return obj;
};

const promisesObject = convertToObj(promisesArray);

// Usage example:
promisesObject.promise1().then((result) => {
  console.log(result);
});

```
