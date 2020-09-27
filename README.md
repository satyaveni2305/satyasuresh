# fuzzy controller for washing machine using fuzzytool kit and matlab.
this is work with both onlineMATLAB and offline MATLAB simulink.
first we need to install or login with the matlab.

after that you can type fuzzy.

you can get the fuzzy tool kit.

Add the Input and output variables to that and save it as (.fis) extension.

Add the rules, change the rules and delete the rules.

after that execute the .m file. 

you can get the desired output of wash time.

here i can take the input as 4 parameters.
Types of clothes - silk, cotton, woolen, jeans 
Types of dirt - greasy, non greasy, mix 
Types of detergent -solid , liquid
Dirtiness of cloths- small, medium, large
This will give us washing time as a 
Output. very short short medium large v.large
 Total number of rules:  4*3*2*3 = 72.

Here is the MATLAB code:
File: washing_machine.fis
[System]
Name='washing_machine'
Type='mamdani'
Version=2.0
NumInputs=4
NumOutputs=1
NumRules=72
AndMethod='min'
OrMethod='max'
ImpMethod='min'
AggMethod='max'
DefuzzMethod='centroid'

[Input1]
Name='Types_of_clothes'
Range=[0 10]
NumMFs=4
MF1='silk':'trimf',[-4.12 -0.0497 2.25838264299803]
MF2='cotton':'trimf',[0.833 5 9.167]
MF3='woolean':'trimf',[5.832 10 14.17]
MF4='jeans':'trimf',[1.37 5 5.41]

[Input2]
Name='Types_of_dirt'
Range=[0 10]
NumMFs=3
MF1='greasy':'trimf',[-4.167 0 4.167]
MF2='non_greasy':'trimf',[0.8333 5 9.167]
MF3='mix':'trimf',[5.833 10 14.17]

[Input3]
Name='Types_of_Detergent'
Range=[0 10]
NumMFs=2
MF1='solid':'trimf',[-4.167 0 4.167]
MF2='liquid':'trimf',[0.8333 5 9.167]

[Input4]
Name='dirtiness_of_cloths'
Range=[0 10]
NumMFs=3
MF1='small':'trimf',[-4.167 0 4.167]
MF2='mediam':'trimf',[0.8333 5 9.167]
MF3='large':'trimf',[5.833 10 14.17]

[Output1]
Name='Washing_time'
Range=[0 30]
NumMFs=5
MF1='very_short':'trimf',[-7.43 7.37 10.6]
MF2='short':'trimf',[4.1715976331361 6.01 10.2]
MF3='medium':'trimf',[6.91076923076923 19.4107692307692 31.9207692307692]
MF4='large':'trimf',[-47.9289940828402 -17.9289940828402 12.0710059171598]
MF5='very_large':'trimf',[0 30 60]

[Rules]
1 1 1 1, 1 (1) : 1
1 2 1 1, 1 (1) : 1
1 3 1 1, 1 (1) : 1
1 1 2 1, 1 (1) : 1
1 2 2 1, 1 (1) : 1
1 3 2 1, 1 (1) : 1
1 3 2 1, 1 (1) : 1
1 1 1 2, 1 (1) : 1
1 1 1 3, 1 (1) : 1
1 1 2 1, 1 (1) : 1
1 1 2 2, 1 (1) : 1
1 1 2 3, 1 (1) : 1
1 1 2 3, 1 (1) : 1
1 1 2 2, 1 (1) : 1
1 1 2 3, 1 (1) : 1
2 1 1 1, 2 (1) : 1
2 1 2 1, 2 (1) : 1
2 1 2 2, 2 (1) : 1
2 1 2 3, 2 (1) : 1
2 2 1 2, 2 (1) : 1
2 2 2 3, 2 (1) : 1
2 2 2 3, 3 (1) : 1
2 3 2 2, 3 (1) : 1
2 3 2 3, 3 (1) : 1
3 1 1 1, 4 (1) : 1
3 3 2 3, 4 (1) : 1
3 3 2 2, 4 (1) : 1
4 1 1 1, 2 (1) : 1
4 2 1 1, 2 (1) : 1
4 3 1 1, 2 (1) : 1
4 1 2 1, 2 (1) : 1
4 2 2 1, 2 (1) : 1
4 3 2 1, 2 (1) : 1
4 1 1 2, 3 (1) : 1
4 2 1 2, 3 (1) : 1
4 3 1 2, 3 (1) : 1
4 3 2 2, 3 (1) : 1
4 2 2 2, 3 (1) : 1
4 1 2 2, 3 (1) : 1
4 1 1 3, 4 (1) : 1
4 2 1 3, 4 (1) : 1
4 3 1 3, 4 (1) : 1
4 3 2 3, 4 (1) : 1
4 2 2 3, 4 (1) : 1
4 1 2 3, 4 (1) : 1
3 1 1 1, 2 (1) : 1
3 3 1 1, 2 (1) : 1
3 2 1 1, 2 (1) : 1
3 3 2 1, 1 (1) : 1
3 2 2 1, 1 (1) : 1
3 1 2 1, 1 (1) : 1
3 1 1 2, 3 (1) : 1
3 2 1 2, 3 (1) : 1
3 3 1 2, 3 (1) : 1
3 3 2 2, 3 (1) : 1
3 2 2 2, 3 (1) : 1
3 1 2 2, 3 (1) : 1
3 1 1 3, 5 (1) : 1
3 2 1 3, 4 (1) : 1
3 3 1 3, 4 (1) : 1
3 3 2 3, 4 (1) : 1
3 2 2 3, 4 (1) : 1
3 1 2 3, 4 (1) : 1
2 1 2 3, 4 (1) : 1
2 2 2 3, 4 (1) : 1
2 3 2 3, 4 (1) : 1
2 1 2 2, 3 (1) : 1
2 2 2 2, 3 (1) : 1
2 3 2 2, 3 (1) : 1
2 3 2 1, 2 (1) : 1
2 2 2 1, 2 (1) : 1
2 1 2 1, 2 (1) : 1


h = readfis ('washing_machine.fis');
a = input ('Types_of_clothes( on a scale of 0-10) =');
b = input ('Types_of_dirt (on a sclae of 0-10) =');
c = input ('Types_of_Detergent (Scale) ? =');
d = input ('dirtiness_of_cloths (on a scale of 0-10)?=');
op = evalfis ([a b c d], h)
disp(['Total Washing Time in minutes: ',num2str(i)]);




