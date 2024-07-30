% Facts
fact(sunny).
fact(weekend).
fact(raining).
fact(weekday).

% Rules
rule(go_beach) :-
    fact(sunny),
    fact(weekend).

rule(watch_movie) :-
    fact(raining).

rule(stay_home) :-
    fact(sunny),
    fact(weekday).

% To deduce a fact
deduce(Fact) :-
    fact(Fact).

deduce(Fact) :-
    rule(Fact),
    \+ fact(Fact),
    assertz(fact(Fact)),
    write('Derived: '), write(Fact), nl.
