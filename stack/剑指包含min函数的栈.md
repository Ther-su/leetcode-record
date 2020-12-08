```js
let minStack=[]
let normalStack=[]
function push(node)
{
    // write code here
  if(minStack.length==0){
    minStack.push(node)
  }else {
    while(minStack.length>0&&minStack[minStack.length-1]>node){
      minStack.pop()
    }
    minStack.push(node)
  }
  normalStack.push(node)
}
function pop()
{
    // write code here
  let del=normalStack.pop()
  if (minStack.length>0&&minStack[0]==del){
    minStack.shift()
  }
}
function top()
{
    // write code here
  return normalStack[normalStack.length-1]
}
function min()
{
    // write code here
  return minStack.length>0&&minStack[0]
}
module.exports = {
    push : push,
    pop : pop,
    top : top,
    min : min
};
```