% Define symptoms
symptom(john, fever).
symptom(john, cough).
symptom(john, headache).
symptom(mary, sore_throat).
symptom(mary, cough).
symptom(mary, fatigue).
symptom(tom, rash).
symptom(tom, fever).
symptom(tom, headache).

% Define diseases and their associated symptoms
disease(flu, [fever, cough, headache, fatigue]).
disease(cold, [cough, sore_throat, fatigue]).
disease(measles, [rash, fever, headache]).

% Rule to diagnose a disease based on symptoms
diagnose(Patient, Disease) :-
    symptom(Patient, Symptom1),
    symptom(Patient, Symptom2),
    symptom(Patient, Symptom3),
    disease(Disease, Symptoms),
    member(Symptom1, Symptoms),
    member(Symptom2, Symptoms),
    member(Symptom3, Symptoms).

% Query example
% ?- diagnose(john, Disease).
