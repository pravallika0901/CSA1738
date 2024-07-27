hanoi(0, _, _, _, []) :- !.
hanoi(N, Source, Destination, Auxiliary, Moves) :-
    N > 0,
    N1 is N - 1,
    hanoi(N1, Source, Auxiliary, Destination, Moves1),
    MoveN = move(Source, Destination),
    hanoi(N1, Auxiliary, Destination, Source, Moves2),
    append(Moves1, [MoveN|Moves2], Moves).
