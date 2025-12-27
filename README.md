# Blog 
What are some differences between interfaces and types in TypeScript?

Typescript is a strongly typed superset of javascript. It helps developers to write clean , strictly typed and maintainable code.
Here I will explain 2 important concept of Ts

---
# Interface v Types in ts

In TypeScript both Interface and Type are used to define data structure. Although both are quite similar, there are some distinct differences between them.. Let's talk about them ...

## Interface
Basaically if our data is related to object or class its better to use interface. It's easy to read and understand and we can extends it and also mix it with multiple interface

example: 

```ts
interface Person{
    name: string;
    age: number ;
}
interface Student extends Person{
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

```ts
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
```


## Question 2 
# What is the use of enums in TypeScript? Provide an example of a numeric and string enum

## Answer:

We use enum (enumaration) when we want our variable will be fixed within some specific value.It helps our code more readable,maintainable and error-free.

## Numeric enum
In numeric enum the variables values are a number.It statrs from very begining and set the first variable's value 0 next will be 1 and so on.
## Example:
```ts
enum Day {
    Saturday, //0
    Sunday, // 1
    Monday, //2
    Tuesday, //3
    Wednesday, //4
    Thursday, //5
    Friday //6
}
const weekend = Day.Saturday
```
Here the first variable starts with default value 0 and will be increase one by one. 

We can also set the value if we want like :

```ts
enum  StatusCode{
    Success = 200,
    ServerError = 500,
    NotFound = 400
}
const handleResponse = (status: StatusCode) => {
    if (status === StatusCode.Success) {
        console.log('Req success');
    }
    else if (status === StatusCode.ServerError) {
        console.log('Server error');
    }
    else if (status === StatusCode.NotFound) {
        console.log('Not found');
    }
};


handleResponse(StatusCode.Success) // output : Req success
```

## String enum

In string enum we have to assign explicit string for each enum.It becomes easily readable and its use in real life project so often.
Example: 
```ts
enum Order{
    Pending = "Pending",
    Shipped = "Shipped",
    Delivered = "Delivered"
}

const OrderStatus = (status: Order) =>{
    if(status === Order.Delivered){
        console.log('Ordered delivered')
    }
    else if(status === Order.Pending){
        console.log('Order pending')
    }
}

OrderStatus(Order.Delivered)
```