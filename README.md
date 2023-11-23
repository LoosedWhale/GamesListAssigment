# Game List Assigment

```java
import java.util.ArrayList;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        ArrayList<Game> gameCollection = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        gameCollection.add(new Game("Minecraft"));
        gameCollection.add(new Game("CSGO"));
        gameCollection.add(new Game("GTA"));
        gameCollection.add(new Game("Valorant"));
        gameCollection.add(new Game("Roblox"));
        gameCollection.add(new Game("Fifa"));
        gameCollection.add(new Game("Forza"));
        gameCollection.add(new Game("Overwatch"));

        while (true) {
            System.out.println("Välj en operation:");
            System.out.println("1. Printa ut alla spel");
            System.out.println("2. Sök efter ett spel");
            System.out.println("3. Lägg till ett nytt spel");
            System.out.println("4. Ersätt ett spel med ett annat spel");
            System.out.println("5. Avsluta programmet");

            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    for (Game game : gameCollection) {
                        System.out.println(game);
                    }
                    break;

                case 2:
                    scanner.nextLine();
                    System.out.println("Vilket spel vill du söka efter:");
                    String searchName = scanner.nextLine();
                    boolean found = false;
                    for (Game game : gameCollection) {
                        if (game.namn.equalsIgnoreCase(searchName)) {
                            System.out.println("Hittat spel; " + game);
                            found = true;
                            break;
                        }
                    }
                    if (!found) {
                        System.out.println("Spelet gittades inte.");
                    }
                    break;

                case 3:
                    scanner.nextLine();
                    System.out.println("Ange namnet på spelet du vill lägga till; ");
                    String newName = scanner.nextLine();
                    Game newGame = new Game(newName);
                    gameCollection.add(newGame);
                    System.out.println("Nytt spel har lagts till:" + newGame);
                    break;
                case 4:
                    scanner.nextLine();
                    System.out.println("Ange spelet du vill ersätta;");
                    String repName = scanner.nextLine();
                    System.out.println("Ange namnet på det nya spelet;");
                    String newGameName = scanner.nextLine();

                    for (int i = 0; i < gameCollection.size(); i++) {
                        Game game = gameCollection.get(i);
                        if (game.namn.equalsIgnoreCase(repName)) {
                            Game newGamerep = new Game(newGameName);
                            gameCollection.set(i, newGamerep);
                            break;
                        }
                    }
                    break;
                case 5:
                    scanner.close();
                    System.exit(0);
                default:
                    System.out.println("Ogitligt val. Försök igen.");
                    break;

            }

        }

    }
}

class Game {
    String namn;

    public Game(String namn) {
        this.namn = namn;
    }

    @Override
    public String toString() {
        return namn;

    }
}

```
# GameListAssigment

This Java program manages a collection of games using an ArrayList. It allows users to perform various operations such as listing all games, searching for a specific game, adding a new game, replacing an existing game, and exiting the program.

## How to Use

1. **Print All Games**
   - Choose option 1 to display a list of all games in the collection.

2. **Search for a Game**
   - Choose option 2 to search for a game by name. Enter the name, and the program will indicate whether the game exists in the collection.

3. **Add a New Game**
   - Choose option 3 to add a new game to the collection. Enter the name of the new game.

4. **Replace a Game**
   - Choose option 4 to replace an existing game. Enter the name of the game you want to replace and the name of the new game.

5. **Exit the Program**
   - Choose option 5 to exit the program.

## Code Explanation

### Main Class (`Main.java`)

- **ArrayList Initialization:**
  ```java
  ArrayList<Game> gameCollection = new ArrayList<>();

An ArrayList named `gameCollection` is created to store instances of the `Game` class.

### Menu Handling:
```java
while (true) {
    // Display menu options and read user choice
    int choice = scanner.nextInt();

    // Switch statement to handle user choices
    switch (choice) {
        // Cases 1-5 handle different operations
        // ...
        default:
            System.out.println("Ogitligt val. Försök igen.");
            break;
    }
}
```

The program uses a `while` loop to repeatedly display a menu, read the user's choice, and execute the corresponding operation using a `switch` statement.

### Game Class (`Game.java`)

## Game Class
```java
class Game {
    String namn;

    public Game(String namn) {
        this.namn = namn;
    }

    @Override
    public String toString() {
        return namn;
    }
}
```
The `Game` class represents a game and has a constructor to set its name. The `toString` method is overridden to provide a string representation of the game.

## How to Contribute

If you want to contribute to this project, feel free to fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License.

Enjoy working with the GameListAssigment!
