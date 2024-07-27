% Facts
parent(john, mary).
parent(john, david).
parent(mary, susan).
parent(david, tom).
parent(david, anna).

male(john).
male(david).
male(tom).

female(mary).
female(susan).
female(anna).

% Rules
father(F, C) :- parent(F, C), male(F).
mother(M, C) :- parent(M, C), female(M).
sibling(X, Y) :- parent(P, X), parent(P, Y), X \= Y.
