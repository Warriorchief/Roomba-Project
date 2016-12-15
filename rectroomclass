
    
#class RectangularRoom

import random

class RectangularRoom(object):

    board=[]
    
    def __init__(self, width, height):
        self.width=width
        self.height=height
        grid=[]
        i=0
        marker=0
        loop=0
        numTiles=self.width*self.height
        #Below, initialize the room as 'grid'. It is a list whose sublists are
        #the tiles in the room. Convertion from the form pos=(x,y) to an item 
        #in this list will be tricky...
        while i<numTiles:
            tile=["","",""]
            tile[0]=i%width
            tile[2]="D" #mark them all as dirty to begin
            grid.append(tile)
            i+=1
        while marker<height:
            for slot in range(loop,loop+width):
                grid[slot][1]=marker
            loop=loop+width
            marker+=1
        self.board=list(grid)

    def cleanTileAtPosition(self, pos):
        #Take in the pos tuple (x,y) and use its indices to change the grid 
        #list item from "D" to "C".
        x=pos[0]
        y=pos[1]
        #find this particular tile in the grid and change it to "C"
        i=0
        while i<len(self.board):
            if self.board[i][0]==x and self.board[i][1]==y:
                #print("okay, changed one tile from D to C, so now board is:")
                self.board[i][2]="C"
            i+=1   
        return self.board
        
    def isTileCleaned(self, m, n):      
        #returns True if (m, n) is cleaned, False otherwise
        i=0
        while i<len(self.board):
            if self.board[i][0]==m and self.board[i][1]==n:
                #print("found it, now will see thether it's currently D or C")
                if self.board[i][2]=="C":
                    return True
            i+=1 
        return False

    def getNumTiles(self):
        #Return the total number of tiles in the room.
        return len(self.board)

    def getNumCleanedTiles(self):
        #Return the total number of clean tiles in the room, an integer
        i=0
        clean=0
        while i<len(self.board):
            if self.board[i][2]=="C":
                clean+=1
            i+=1
        return clean
        
    def getRandomPosition(self):
        #Return a random position inside the room, a position object
        xrand=random.random()*self.width
        yrand=random.random()*self.height
        pos=(int(xrand),int(yrand))
        return pos

    def isPositionInRoom(self, pos):
        #Return True if the pos object is inside the room, False otherwwise
        if 0<=pos[0]<self.width and 0<=pos[1]<self.height:
            return True
        return False
