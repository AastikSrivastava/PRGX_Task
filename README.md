# PRGX_Task
Cricket match

/* 
Creating Player class with thier respective subclasses and to create a TeamScore class to calulcate win / lose team score. 
*/


public class CricketPlayers
{


  public static void m1()
{

Player players1[] = new Player[11];

players1[0] = new Batsmen("Sachin", 18 , 0 , 0);
players1[1] = new WicketKeeper("Dhoni", 153, 1 , 2);
players1[2] = new Batsmen("Shewag", 102, 1 , 1);
players1[3] = new Batsmen("Yuvraj", 23, 0 , 0);
players1[4] = new Batsmen("Kohli", 75, 0 , 1);
players1[5] = new Batsmen("Raina", 27, 0 , 0);
players1[6] = new Batsmen("Rohit", 56, 0 , 1);
players[7] = new Bowler("Harbhajan", 13 , 3 , 4);
players1[8] = new Bowler("Zaheer",  8 , 0 , 2);
players1[9] = new Bowler("Umesh",  2 , 2 , 0);
players1[10] = new Bowler("Aswin",  2 , 1 , 1);


Player players2[] = new Player[11];

players2[0] = new Batsmen("Ravinder", 78, 0, 1);
players2[1] = new WicketKeeper("Ashwin", 153, 6021, 120, 67);    
players2[2] = new Batsmen("JK", 11, 0, 0);
players2[3] = new Batsmen("Lal Singh", 23, 0, 0);
players2[4] = new Batsmen("Rahul", 175, 1, 2, );
players2[5] = new Batsmen("Gmb", 34, 0, 0);
players2[6] = new Batsmen("Panikae", 25, 0 , 0 );
players2[7] = new Bowler("Harbhajan", 18 , 2, 4);
players2[8] = new Bowler("Zaheer", 19 , 1, 4);
players2[9] = new Bowler("Umesh", 10 , 0, 0);
players2[10] = new Bowler("Aswin", 3 , 3, 4);

int team1Score =0;
int team2Score =0;



// printing each player of team 1 score cards
for(Player player : players1)
{
player.print();
team1Score = player.getRunsScored();
System.out.println();
System.out.println("---------------------");

}


// printing each player of team 2 score cards
for(Player player : players2)
{
player.print();
team2Score = player.getRunsScored();
System.out.println();
System.out.println("---------------------");

}




// deciding winner of match
boolean check = TeamScore.createWinner(team1Score ,  team2Score);

  if(team1Score>0 && team2Score == 0){
        System.out.println("Team 1 has perfect record ! ");
  }

  if(team2Score>0 && team1Score == 0){
        System.out.println("Team 2 has perfect record ! ");
  }

 if(check) {
          System.out.println("Win "+ team1Score);
          System.out.println("Loss "+ team2Score);
          } else {
          System.out.println("Win "+ team1Score);
          System.out.println("Loss "+ team2Score);
}

}
}





abstract class Player
{

String name;
int runsScored;

Player(String name, int runsScored)
{
this.name = name;
this.runsScored = runsScored;
}


void bat()
{
}

void makeSomeRuns()
{
}

void print()
{
System.out.print(name + " scored " + runsScored + " runs.");
}
}






class Batsmen extends Player
{

int numberOfCenturies;
int numberOfHalfCenturies;
// Assume have added Getter & setter

Batsmen(String name, int runsScored, int numberOfCenturies, int numberOfHalfCenturies)
{
super(name, runsScored);
this.numberOfCenturies = numberOfCenturies;
this.numberOfHalfCenturies = numberOfHalfCenturies;
}

void openInnings()
{
}

void makeCentury()
{
}

void makeHalfCentury()
{
}

void print()
{
super.print();
System.out.print(" He is a good batsmen and made " + numberOfCenturies + " centuries and " + numberOfHalfCenturies + " half centuries.");
}
}







class Bowler extends Player
{
int numberOfWickets;
int numberOf5WicketInnings;

// Assume have added Getter & setter



Bowler(String name, int runsScored, int numberOfWickets, int numberOf5WicketInnings)
{
super(name, runsScored);
this.numberOfWickets= numberOfWickets;
this.numberOf5WicketInnings = numberOf5WicketInnings;
}

void openInnings()
{
}

void bowlYorkers()
{
}

void takeWickets()
{
}

void print()
{
super.print();
System.out.print(" He is a good bowler and has taken " + numberOfWickets + " wickets. He has " + numberOf5WicketInnings + " 5WI(5-Wicket Innings) in his account.");
}

}





class WicketKeeper extends Player

{
int numberOfCatches;
int numberOfStumpings;

// Assume have added Getter & setter

WicketKeeper(String name, int runsScored, int numberOfCatches, int numberOfStumpings)
{
super(name, runsScored);
this.numberOfCatches = numberOfCatches;
this.numberOfStumpings = numberOfStumpings;
}

void keepWickets()
{
}

void stumpBatsmen()
{
}

void makeAppeals()
{
}



void print()
{
super.print();
System.out.print(" He keeps the wickets and has " + numberOfCatches + " catches and " + numberOfStumpings + " stumpings in his account.");
}


}





 class TeamScore {

        public static boolean createWinner(int points1, int points2)  
         {
          if (points1 > points2)
          {
          return true;
          }
                else
         {
          return false;  
         } 

         return false;
         }
      
}
