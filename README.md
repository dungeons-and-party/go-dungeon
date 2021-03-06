go-dungeon
==========

Random dungeon generator written in go. Based on the method described here: http://journal.stuffwithstuff.com/2014/12/21/rooms-and-mazes/

Run as a Server and Generate Images
-----------------------------------
Running the program as a server will allow you to configure the parameters of the dungeon through a web page. The currently available inputs are dungeon width, dungeon height, how many times to try to place random rooms, minimum room size, maximum room size, how large each tile is in pixels, and the random integer seed to use. To run the program as a server:

 * run the command `go run dungeon.go -server`
 * navigate to `localhost:8080`
 * click the "Generate Dungeon" button to generate another random dungeon

Example Image Output
--------------------
![alt tag](http://i.imgur.com/rLqddnJ.png)

Run in Command Line and Generate ASCII
--------------------------------------
`go run dungeon.go`

Legend
------
`0` - wall

`=` - room floor

`|` - door

`-` - tunnel

Sample ASCII Output
-------------------

```shell
Creating empty dungeon...
Creating rooms...
Creating tunnels...
Identifying edges...
Conneting regions...
Trimming tunnels...
Dungeon: ( 40 , 40 ) Regions:  13
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
0 0 0 0 0 0 0 = = = = = = = = 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 
0 0 0 0 0 0 0 = = = = = = = = 0 0 0 0 0 0 0 = = = = = = 0 = = = = = = 0 0 0 0 0 
0 0 0 0 0 0 0 = = = = = = = = 0 0 0 0 0 0 0 = = = = = = 0 = = = = = = 0 0 0 0 0 
0 0 - - - 0 0 = = = = = = = = 0 0 0 0 0 0 0 = = = = = = 0 = = = = = = 0 0 0 0 0 
0 - - 0 - 0 0 = = = = = = = = 0 0 0 0 0 0 0 = = = = = = 0 = = = = = = 0 0 0 0 0 
0 - 0 0 - - | = = = = = = = = 0 0 0 0 0 0 0 = = = = = = 0 = = = = = = 0 0 0 0 0 
0 - - 0 0 0 0 = = = = = = = = 0 0 0 0 0 0 0 = = = = = = 0 = = = = = = 0 0 0 0 0 
0 0 - - 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 = = = = = = 0 0 0 0 | 0 0 0 0 0 0 0 
0 0 0 - - 0 0 0 0 0 0 0 0 0 0 = = = = = 0 0 0 0 0 | 0 0 0 0 0 - - - - 0 0 0 0 0 
0 0 0 0 - 0 0 0 0 0 0 0 0 0 0 = = = = = 0 0 0 0 - - - - - - - - 0 0 - 0 0 0 0 0 
0 0 0 0 - 0 0 0 0 0 0 0 0 0 0 = = = = = 0 0 0 - - 0 - 0 0 0 0 0 0 - - - 0 0 0 0 
0 0 0 0 - 0 = = = = = = = = 0 = = = = = 0 0 0 - 0 0 | 0 0 0 0 0 - - 0 - - - - 0 
0 - - - - 0 = = = = = = = = 0 = = = = = 0 - - - 0 0 = = = = = 0 - 0 0 0 0 0 - 0 
0 - 0 0 0 0 = = = = = = = = 0 0 | 0 0 0 0 - 0 0 0 0 = = = = = 0 - - 0 0 0 - - 0 
0 - - 0 0 0 = = = = = = = = 0 0 - - 0 0 0 - 0 0 0 0 = = = = = 0 0 - 0 - - - 0 0 
0 0 - 0 0 0 = = = = = = = = 0 0 0 - - - - - 0 0 0 0 = = = = = 0 0 - 0 - 0 0 0 0 
0 0 - 0 0 0 0 0 0 0 | 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 = = = = = 0 0 - 0 - - 0 0 0 
0 - - 0 = = = = = = = 0 0 = = = = = 0 0 = = = = = 0 = = = = = 0 - - 0 0 - - - 0 
0 - 0 0 = = = = = = = 0 0 = = = = = 0 0 = = = = = 0 0 0 0 0 0 0 - 0 0 0 0 0 - 0 
0 - 0 0 = = = = = = = 0 0 = = = = = 0 0 = = = = = 0 - - - - - - - - - 0 0 - - 0 
0 - 0 0 = = = = = = = 0 0 = = = = = 0 0 = = = = = 0 - 0 0 0 0 0 0 0 | 0 - - 0 0 
0 - - 0 = = = = = = = 0 0 = = = = = 0 0 = = = = = 0 - 0 = = = = = = = 0 - 0 0 0 
0 0 - 0 = = = = = = = 0 0 = = = = = 0 0 = = = = = 0 - 0 = = = = = = = 0 - 0 0 0 
0 0 - 0 = = = = = = = 0 0 0 0 0 0 | 0 0 = = = = = | - 0 = = = = = = = 0 - 0 0 0 
0 0 - 0 0 0 0 0 0 0 | 0 - - - - - - 0 0 0 0 0 0 0 0 0 0 = = = = = = = 0 - - 0 0 
0 - - 0 = = = = = = = 0 - 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 = = = = = = = 0 0 - 0 0 
0 - 0 0 = = = = = = = 0 - 0 = = = = = = = = = 0 0 0 0 0 0 0 0 0 0 0 0 0 0 - 0 0 
0 - - 0 = = = = = = = 0 - 0 = = = = = = = = = 0 0 0 0 0 0 0 0 0 0 0 0 - - - 0 0 
0 0 - 0 = = = = = = = 0 - 0 = = = = = = = = = 0 0 0 0 - - - 0 0 0 0 0 - 0 0 0 0 
0 - - 0 = = = = = = = 0 - 0 = = = = = = = = = 0 0 - - - 0 - - 0 0 0 0 - 0 0 0 0 
0 - 0 0 = = = = = = = 0 - 0 = = = = = = = = = 0 0 - 0 0 0 0 - 0 0 - - - 0 0 0 0 
0 - 0 0 = = = = = = = | - 0 = = = = = = = = = 0 0 - 0 0 0 0 - 0 0 - 0 0 0 0 0 0 
0 - - 0 0 0 0 0 0 0 0 0 - 0 | 0 0 0 0 0 0 0 0 0 - - 0 0 0 0 - - 0 - 0 0 0 0 0 0 
0 0 - - - - - - - - - - - - - - - - - - - - - - - 0 0 0 0 0 0 - - - 0 0 0 0 0 0 
0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0
```
