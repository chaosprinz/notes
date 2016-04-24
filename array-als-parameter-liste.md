# Array als Parameter-liste

## Quicky
const meineFunktion = function(eins,zwei){
  console.log("${eins} und ${zwei}"");
}
parameter = ("hoho, haha")
meineFunktion.apply(this, parameter)

(https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)[Details]