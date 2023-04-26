# How to use it

Since every class we create in our project needs to be able to use p5 functions, this package solves the problem by exposing the sketch object. So we can import it into any class and use p5 functions as needed.

main.js
```javascript
import p from 'p5-sketch'
import MyExternalObject from './my-external-object'

let obj

p.setup = () => {
  p.createCanvas(600, 600)
  obj = new MyExternalObject()
}

p.draw = () => {
  p.background('PapayaWhip')
}
```

my-external-object.js
```javascript
import p from 'p5-sketch'

export default class MyExternalObject {
  constructor() {
    this.x = 300
    this.y = 300
  }

  draw() {
    p.noStroke()
    p.fill('red')
    p.circle(this.x, this.y, 100)
  }
}
```



