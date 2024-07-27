% Facts: fruit and its color
fruit_color(apple, red).
fruit_color(banana, yellow).
fruit_color(grape, purple).
fruit_color(lemon, yellow).
fruit_color(orange, orange).
fruit_color(cherry, red).
fruit_color(plum, purple).

% Rule to find fruits of a specific color
fruits_of_color(Color, Fruit) :-
    fruit_color(Fruit, Color).

% Rule to list all fruits of a specific color using backtracking
list_fruits_of_color(Color) :-
    fruits_of_color(Color, Fruit),
    writeln(Fruit),
    fail.
list_fruits_of_color(_).
