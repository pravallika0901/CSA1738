planet(mercury, 1, terrestrial).
planet(venus, 2, terrestrial).
planet(earth, 3, terrestrial).
planet(mars, 4, terrestrial).
planet(jupiter, 5, gas_giant).
planet(saturn, 6, gas_giant).
planet(uranus, 7, gas_giant).
planet(neptune, 8, gas_giant).
planetName(Order, Name) :-
    planet(Name, Order, _).
planetType(Name, Type) :-
    planet(Name, _, Type).
terrestrialPlanets(Planets) :-
    findall(Name, planet(Name, _, terrestrial), Planets).
gasGiants(Planets) :-
    findall(Name, planet(Name, _, gas_giant), Planets).
