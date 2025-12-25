# Blog 
What are some differences between interfaces and types in TypeScript?

Typescript is a strongly typed superset of javascript. It helps developers to write clean , strictly typed and maintainable code.
Here I will explain 2 important concept of Ts

---
# Interface v Types in ts

In TypeScript both Interface and Type are used to define data structure. Though both are quite same but there are some distinc difference between this two. Let's talk about them ...

## Interface
Basaically if our data is related to object or class its better to use interface. It's easy to read and understand and we can extends it and also mix it with multiple interface

example: 
```
interface Person{
    name: string;
    age: number ;
}
interface Student extends Perosn{
    roll:number;
    class: string;
}

const sakib: Student = {
    name:"sakib",
    age: 30,
    roll:3,
    class: "Ten"
}
```
## Type

The main difference between interface and type is in Type we can define premitive data type here.
By using type we can easily use the union and intersaction

```
type ProductStatus = "Available" | "Out of stock"
type Product ={
    id:number;
    name:string;
    price:number;
    status:ProductStatus
}
const phone: Product = {
    id: 1011,
    name: "Iphone",
    price: 5000,
    status: "Available"
}

