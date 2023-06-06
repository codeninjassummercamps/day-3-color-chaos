# Day 3 Color Chaos

```template
player.onChat("red", function () {
    agent.teleport(world(6, 0, 6), WEST)
})
player.onChat("orange", function () {
    agent.teleport(world(4, 0, 6), WEST)
})
player.onChat("yellow", function () {
    agent.teleport(world(2, 0, 6), WEST)
})
player.onChat("green", function () {
    agent.teleport(world(0, 0, 6), WEST)
})
player.onChat("blue", function () {
    agent.teleport(world(-2, 0, 6), WEST)
})
player.onChat("purple", function () {
    agent.teleport(world(-4, 0, 6), WEST)
})
loops.forever(function(){
    if(blocks.testForBlock(RED_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.turn(TurnDirection.Left)
    }
    if(blocks.testForBlock(ORANGE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(BACK, 1)
        agent.setItem(SHROOMLIGHT, 1, 1)
        agent.place(FORWARD)
    }
    if(blocks.testForBlock(YELLOW_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        mobs.spawn(SHEEP, agent.getPosition())
        agent.move(BACK, 1)
    }
    if(blocks.testForBlock(LIME_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.teleportToPlayer()
        agent.move(BACK, 1)
        agent.attack(FORWARD)
    }
    if(blocks.testForBlock(LIGHT_BLUE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(BACK, 1)
        agent.setItem(DIAMOND_BLOCK, 64, 1)
        agent.dropAll(FORWARD)
    }
    if(blocks.testForBlock(PURPLE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(UP, 1)
        agent.move(DOWN, 1)
    }
})
```

## Color Chaos

What's the agent going to do when it steps on the different colors? You will write a sign with your guess, then use the chat commands to check your guess!

## Red 1

We have a chat command "red," but all it's doing is teleporting the agent. We need to look at the code that starts with ``||loops.forever||``.

```blocks
loops.forever(function(){

})
```

## Red 2

Now that we've found the code, let's figure out what it means. The first thing we notice is the ``||logic.if||`` around all the rest of the code. This is a Conditional. We use it to decide whether to do something based on a yes/no question.

```blocks
loops.forever(function(){
if(blocks.testForBlock(RED_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.turn(TurnDirection.Left)
}
})

```

## Red 3

In this code, the ``||logic.if||`` looks quite complicated, but all it is asking is "Is there a red concrete block underneath the agent?" If yes, it will run the code inside. Otherwise, it will skip to the next part of the code.

```blocks
loops.forever(function(){
if(blocks.testForBlock(RED_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.turn(TurnDirection.Left)
}
})
```

## Red 4

Now that we know where to look, what do you think will happen when the agent steps on the red concrete? Leave the code builder and place a sign near the red concrete with your guess. Make sure you come back to the code builder after!

```blocks
loops.forever(function(){
if(blocks.testForBlock(RED_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.turn(TurnDirection.Left)
}
})
```

## Orange 1

Now that we've guessed what red will do, let's look at orange! Can you find the code that will make the agent do something when standing on orange concrete?

```blocks
loops.forever(function(){
    if(blocks.testForBlock(ORANGE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(BACK, 1)
        agent.setItem(SHROOMLIGHT, 1, 1)
        agent.place(FORWARD)
    }
})
```

## Orange 2

If you found the ``||logic.if||`` for orange concrete on your own, great work! If not, use the hint to help you locate the right section of code.

```blocks
loops.forever(function(){
    if(blocks.testForBlock(ORANGE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(BACK, 1)
        agent.setItem(SHROOMLIGHT, 1, 1)
        agent.place(FORWARD)
    }
})
```

## Orange 3

Just like what we did for red, try to figure out what the agent will do when standing on orange concrete. When you think you've got it, leave the code builder and place a sign with your guess near the orange concrete. Don't forget to come back to the Code Builder after!

```blocks
loops.forever(function(){
    if(blocks.testForBlock(ORANGE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(BACK, 1)
        agent.setItem(SHROOMLIGHT, 1, 1)
        agent.place(FORWARD)
    }
})
```

## Yellow

Let's repeat the process for yellow. Find the ``||logic.if||`` for yellow concrete, then write a sign with your guess and come back to the code builder!

```blocks
loops.forever(function(){
    if(blocks.testForBlock(YELLOW_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        mobs.spawn(SHEEP, agent.getPosition())
        agent.move(BACK, 1)
    }
})
```

## Green

Next we'll try green. Find the ``||logic.if||`` for lime concrete, then write a sign with your guess and come back to the code builder!

```blocks
loops.forever(function(){
    if(blocks.testForBlock(LIME_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.teleportToPlayer()
        agent.move(BACK, 1)
        agent.attack(FORWARD)
    }
})
```

## Blue

Time to figure out blue. Find the ``||logic.if||`` for light blue concrete, then write a sign with your guess and come back to the code builder!

```blocks
loops.forever(function(){
    if(blocks.testForBlock(LIGHT_BLUE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(BACK, 1)
        agent.setItem(DIAMOND_BLOCK, 64, 1)
        agent.dropAll(FORWARD)
    }
})
```
## Purple

Last one! Try to guess what the agent will do when standing on purple concrete? Find the ``||logic.if||`` for purple concrete, then write a sign with your guess and come back to the code builder!

```blocks
loops.forever(function(){
    if(blocks.testForBlock(PURPLE_CONCRETE, world(agent.getPosition().getValue(Axis.X), agent.getPosition().getValue(Axis.Y) - 1, agent.getPosition().getValue(Axis.Z)))){
        agent.move(UP, 1)
        agent.move(DOWN, 1)
    }
})
```

## Time to Test

You placed signs with your guesses near all the colors of concrete, now it's time to check your guesses! Use the chat commands red, orange, yellow, green, blue, and purple to see what the agent does when standing on the colors! Were your guesses right?

## Activity Complete!

You did it! You explored conditionals and learned about ``||logic.if||`` blocks!
