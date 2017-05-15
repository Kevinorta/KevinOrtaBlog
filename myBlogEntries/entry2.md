# mancala blog #2
### game progress

---------------------------------------

## logic:
As I said in the last blog entry, this game is going to be logic extensive. Last
week I was able to change the value of a single box when I clicked it. This week
I had to find out how to make each box change its own value and the value of the 
surrounding boxes. I numbered every box with its own id. Then instead of creating
seperate functions for each box I realized it would be easier to make only one function
and have different arguments for each one corresponding to the block number. It looked
like this.
```html
<div id="game">
    <table>
      <tr>
        <td rowspan="2" id="b14">0</td>
        <td onclick="p2(13)" id="b13">4</td>
        <td onclick="p2(12)" id="b12">4</td>
        <td onclick="p2(11)" id="b11">4</td>
        <td onclick="p2(10)" id="b10">4</td>
        <td onclick="p2(9)" id="b9">4</td>
        <td onclick="p2(8)" id="b8">4</td>
        <td rowspan="2" id="b7">0</td>
      </tr>
      <tr>
        <td onclick="p1(1)" id="b1">4</td>
        <td onclick="p1(2)" id="b2">4</td>
        <td onclick="p1(3)" id="b3">4</td>
        <td onclick="p1(4)" id="b4">4</td>
        <td onclick="p1(5)" id="b5">4</td>
        <td onclick="p1(6)" id="b6">4</td>
      </tr>
    </table>
  </div>
```


## multiplayer:
This is where I realized how much more difficult this was going to be. Just making the
logic was going to be a big problem because I had to impliment two players. I had
to make two different functions for each player and make it so they could only go
on their turn. I was able to semi impliment this like so
```javascript 
if (turn == "player 1" && moves > 0)  
````
```javascript 
else if (turn == "player 2") {
      alert("its not ur turn fam");
    }
    else {
      alert("you got no turns, go again");
    }
    if (turnsame==0){
      alert("player 2 turn")
      turn="player 2"
    }else{
      alert("its player 1 again")
      turn = "player 1";
      
    }
````

There are still some bugs I need to work out in this, but that is for later.
This did give me an idea for ditching ActiveRecord and the leaderboard 
and implimenting an online multiplayer. I need to change my topic now or else I won't
be able to later.


## websockets:
I have never heard of websockets before. When researching how to create small multiplayer 
games I came across a lot of people reccomending websockets. I quickly realized that 
this would be the best method of making my game an online multiplayer game and decided
to go with it. Next week I will dive more into websockets and their uses and implimentation.


## takeaways:
* Prioritize. 
   Make sure you are working out the most important issues first. When working out
   the two player element of this game I created many bugs. I left it in a semi-functioning
   condition but decided to move on to websockets because at this point that would make
   bigger impact then some bugs I can work out later.