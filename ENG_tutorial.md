## How far did the ISS travel? @unplugged
<div style="display: flex; justify-content: space-around;">
  <img src="https://github.com/ESERODanmark/isstravellingdistance/blob/master/ikon_issDist.png?raw=true" alt="DampVibrations" width="300"/>
  <img src="https://github.com/ESERODanmark/multicounter/blob/master/clickTip.gif?raw=true" alt="ClickTip" width="300"/>
</div>


## Coding of button A
When button A is pressed, @boardname@ should start a timer. Create the variable `||variables:startTime||`.

## Coding of button A 
Drag the block `||variables: set startTime to 0||` into the block `||input.button A||`

```blocks
input.onButtonPressed(Button.A, function () {
    startTime = (0)
})
```

## Coding of button A
Drag the block `||input.runningTime (ms)||` into `||variables: set startTime to 0||`.

```blocks
input.onButtonPressed(Button.A, function () {
    startTime = input.runningTime()
})
```

## Coding of button A
Drag the block `||basic.show LEDs||` into `||variables: set||`

```blocks
input.onButtonPressed(Button.A, function () {
    startTime = input.runningTime()
    basic.showLeds(`
    . . . . .
    . . . . .
    . . . . .
    . . . . .
    . . . . .
    `)
})
```

## Coding of button A
Draw a symbol to indicate that the timing has started.

```blocks
input.onButtonPressed(Button.A, function () {
    startTime = input.runningTime()
    basic.showLeds(`
    . . . . .
    . . # . .
    . . # . .
    . . # . .
    . . . . .
    `)
})
```

## Coding of button B
Find a block for `||input.button B||`

```blocks
input.onButtonPressed(Button.B, function () {
})
``` 

## Coding of button B 
Create the variable `||variables:endTime||`


## Coding of button B 
Drag the block `||variables: set endTime to 0||` into the button B block.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = 0
})
```

## Coding of button B 
Drag the block `||input: runningTime (ms)||` into the block `||variables: set endTime to 0||`

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
})
```

## Coding of button B 
Create the variable `||variables:calculatedTime||`

## Coding of button B 
Drag the block `||variables: set calculatedTime til 0||` into `||variables: set endTime to runningTime (ms)||`

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = 0
})
```

## Coding of button B 
Drag the block `||math:0 - 0||` into `||variables: set calculatedTime to 0||`. 

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    measuredTime = 0 - 0
})
```

## Coding of button B  
Drag the block `||variables: endTime||` into the place of the first 0.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    measuredTime = endTime - 0
})
```

## Coding of button B  
Drag the block `||variables: startTime||` into the place of the second 0.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    measuredTime = endTime - startTime
})
```

## Coding of button B 
@boardname@ measures time in milliseconds. We need to measure in seconds. 
Therefore, calculatedTime should be divided by 1000. Insert the block `||variables: set calculatedTime to 0||`.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime = 0
})
```

## Coding of button B 
Drag `||math:0 / 0||` into `||variables: set calculatedTime to 0||`.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime = 0 / 0
})
```

## Coding of button B 
Drag `||variables: calculatedTime||` into the place of the first 0.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime = calculatedTime / 0
})
```

## Coding of button B 
Write 1000 in the second 0's place.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime = calculatedTime / 1000
})
```

## Coding of button B 
Create the variable `||variables:distance||`

## Coding of button B  
Insert the block `||variables: set distance to 0||`

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    measuredTime = endTime - startTime
    measuredTime = measuredTime / 1000
    distance = 0
})
```

## Coding of button B  
Drag the block `||math:0 * 0||` into `||variables: set distance to 0||`

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime = measuredTime / 1000
    distance = 0 * 0
})
```

## Coding of button B  
Insert `||variables: calculatedTime||` into the place of the first 0. 

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime= calculatedTime / 1000
    distance = calculatedTime * 0
})
```

## Coding of button B  
Write 7.77 in the second 0's place. 7.77 is the speed of the ISS measured in km/s. Note: Use a period instead of a comma.

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime= calculatedTime / 1000
    distance = calculatedTime * 7.77
})
```

## Coding of button B  
Insert the block `||basic.show number||`
```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime= calculatedTime / 1000
    distance = calculatedTime * 7.77
})
```

## Coding of button B  
Insert the variable `||variables: distance ||` into `||basic.show number||`

```blocks
input.onButtonPressed(Button.B, function () {
    endTime = input.runningTime()
    calculatedTime = endTime - startTime
    calculatedTime= calculatedTime / 1000
    distance = calculatedTime * 7.77
    basic.showNumber(distance)
    basic.showString(" km")})
```


## Congratulations!
Your code is ready. Press done!


```template
input.onButtonPressed(Button.A, function () {
}
```