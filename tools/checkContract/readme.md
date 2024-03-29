# Check contract tool

## Description

This tool offers easy support for checking whether the transferred value meets the contract.

## Example use case

```jsx
import { contractValidator } from "./useContract";

const user = {
  name: "John Doe",
  age: 25,
  email: "johndoe@example.com",
};

const contract = {
  name: (val: unknown) => typeof val === "string",
  age: (val: unknown) => typeof val === "number",
  email: (val: unknown) => typeof val === "string" && (val as string).includes("@"),
};

const isValid = contractValidator(user, contract).checkContract();
console.log(isValid); // true
```
