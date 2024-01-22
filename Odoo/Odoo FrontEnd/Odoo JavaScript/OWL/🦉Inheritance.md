```Javascript
class Child extends Component {  
  static template = xml`<div><t t-esc="props.a"/><t t-esc="props.b"/></div>`;  
}  
class Parent extends Component {  
  static template = xml`<div><Child a="state.a" b="'string'"/></div>`;  
  static components = { Child };  
  state = useState({ a: "fromparent" });  
}
```

In this example, the Child component receives two props (a and b) from its parent (Parent). 
The values are collected into a props object by Owl, with each value evaluated in the context of the parent. 
Consequently, `props.a` equals `fromparent,` and `props.b` equals `string`.