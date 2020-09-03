# Hello-World
Learning Basics of GitHub
This is additional writing that is not currently on the main branch
NoOfStudents = 6000;
TeachingStaff = 150;
NonTeachingStaff = 20;
Total = NoOfStudents + TeachingStaff ...
   + NonTeachingStaff;
disp(Total);

a = 5; b = 7;
c = a + b
d = c + sin(b)
e = 5 * d
f = exp(-d)

x=3 %logical 1 =true,logical 0 =false
isinteger(x) %So why is this false then?
isscalar(x) %How is it both scalar and vector?
isvector(x)

a=[1 2 3;4 5 6;7 8 9];
b=[10 11 12; 13 14 15; 16 17 18];
c=a*b %standard matrix multiplication
d=a.*b %each singular element multiplied by the corresponding singular element in the other matrix
e=b/a %matrix right division (matrix left division also possible with \)
f=b./a %array right division (array left division also possible with \)
g=a*inv(b) %a multiplied by inverse of b
h=a' %this is a transposision, an array transposition is also possible using a . (adding a . always causes the array version to be done)

9>10
10~=11 %~= means is not equal

%Element-wise logical operators operate element-by-element on logical arrays...
%The symbols &, |, and ~ are the logical array operators AND, OR, and NOT.

%Short-circuit logical operators allow short-circuiting on logical operations...
%The symbols && and || are the logical short-circuit operators AND and OR.
a = 5;
b = 20;
   if ( a && b ) %ie: are both a and b integers and not 0?
      disp('Line 1 - Condition is true'); %disp= "display what is in the brackets and within the apostrophes"
   end
   if ( a || b ) %ie: is either a or b an integer and not 0?
      disp('Line 2 - Condition is true');
   end
   
   % lets change the value of  a and b 
   a = 0;
   b = 10;
   
   if ( a && b )
      disp('Line 3 - Condition is true');
   else
      disp('Line 3 - Condition is not true');
   end
   
   if (~(a && b))
   
      disp('Line 4 - Condition is true');
   end
   %I don't really get logical operators and also especially don't get bitwise and set operations yet
   
   false
   false(4)
   
   a=100
   if a==10 disp('Line 1 is True')
   elseif a==20 disp('Line 2 is True')
   else disp('Lines and 1 and 2 are False')
   end
       
Grade='D';
switch(Grade) %re-look over this
case 'A' 
    disp('Great!'); %This "disp" must be on a different line
    case 'B'
        disp('Good');
        case 'C' 
            disp('Okay');
    otherwise
        disp('Invalid Grade');
end
                
a = 100;
b = 200;
switch(a) %re-look over this double switch
   case 100 
      fprintf('This is part of outer switch, %d\n', a ); %"fprintf" is an alternative to "disp" - they both do the same thing)
      switch(b) 
         case 200
            fprintf('This is part of inner switch, %d\n', a );
      end
end

fprintf('Exact value of a is : %d\n', a ); %re-look over how and when disp, fprintf and sprintf work
fprintf('Exact value of b is : %d\n', b );  

sprintf('Hello') %"sprintf" also works as a more adaptable version of "fprintf" and "disp" - still does generally same thing. (Sprintf is used for formatting data into a string or character array, eg: str=sprintf(formatSpec,A1,...,An)  formats the data in arrays A1,...,An using the formatting operators specified by formatSpec and returns the resulting text in str. The sprintf function formats the values in A1,...,An in column order. If formatSpec is a string, then so is the output str. Otherwise, str is a character vector.)

%round(x) rounds the precision figure of x to an integer, eg: str=sprintf('%d',round(pi)) gives str='3'

%Loops: (re-look over loops)

%While loop

a=15
while(a<20)
fprintf('Value of a: %d\n', a);
a=a+2;
end

%For looop

for b=10:15 %means "for b=10 to 15"
fprintf('value of b: %d\n', b);
end

for a = 1.0: -0.1: 0.0 %in the style of... start point:intervals:end point
   disp(a)
end

for a = [24,18,19; 17,23,28] %This is the "valArray" For Loop, I don't really get this one 
   disp(a)
end

%Nested Loops (Nested For loops and Nested While loops)

for i = 2:100 %don't really get nested loops
   for j = 2:100
      if(~mod(i,j)) %mod(a,m) gives the remainder after a is divided by m.
         break; % if factor found, not prime
      end 
   end
   if(j > (i/j))
      fprintf('%d is prime\n', i);
   end
end
   
b=20
while(b>10)
    disp('value of b:') 
    disp(b)
    b=b-1;
    if(b==15)
        break; %can also be used to terminate a for loop
    end
end

%Tutorial currently using: https://www.tutorialspoint.com/matlab/matlab_break_statement.htm

b=15;
while b<20
    b=b+1;
    if b==18 
 continue; %The b=18 value is skipped
    end
    fprintf('Value of b: %d\n',b)
end

a = 9; 
while a < 20
   a = a + 1; 
   if a == 15
      continue; %means "skip the iteration, ie: a=15 iteration is skipped"
   end 
fprintf('value of a: %d\n', a);
end

v=[3;5;7;9];
v(3) %3rd element in vector

v=[1 2 3 4];
v(1:3)

r1 = [ 1 2 3 4 ];
r2 = [5 6 7 8 ];
r = [r1,r2] %gives 1 row
rMat = [r1;r2] %gives 2 rows
 
c1 = [ 1; 2; 3; 4 ];
c2 = [5; 6; 7; 8 ];
c = [c1; c2] %gives 1 column
cMat = [c1,c2] %gives 2 columns

%Matrices:

a=[1 2 3 4 5; 5 4 3 2 1; 1 2 3 4 5; 5 4 3 2 1; 1 2 3 4 5] %Use square brackets, a semicolon gives a new row
a(2,5) %2nd row, 5th column
a(:,4) %4th column
a(:,2:4) %columns 2 to 4
a(4,:)=[] % deletes 4th row
b = [ 1 2 3 ; 4 5 6; 7 8 9];
new_mat = b([2,3,2,3],:) % adds a 4th row

a = [ 10 12 23 ; 14 8 6; 27 8 9]
b = [ 12 31 45 ; 8 0 -9; 45 2 11]
c = [a, b] %concatenating matrices horizontally
d = [a; b] %concatenating matrices vertically

a = [ 1 2 3; 2 3 4; 1 2 5]
det(a) %determinent of matrix

a = [ 1 2 3; 2 3 4; 1 2 5]
inv(a) %inverse of matrix

%Arrays (Matrices and Vectors are just 1-dimensional and 2-dimensional types of arrays)

zeros(5) %creates a matrix of zeros
ones(3) %creates matrix of ones
eye(4) %creates identity matrix
rand(2,3) % creates matrix with random numbers between 0 and1

%I really don't get how to create multi-dimensional arrays (ie: not 1/2-D)

a(:, :, 2)= [ 1 2 3; 4 5 6; 7 8 9]
disp(a)
b=rand(2,3,4)

a = [9 8 7; 6 5 4; 3 2 1]; %array to be concatenated
b = [1 2 3; 4 5 6; 7 8 9]; %array to be concatenated
c = cat(3, a, b, [ 2 3 1; 4 7 8; 3 9 0]) %done in the form 3-D array =cat(dimension along which to concatenate the arrays, a, b)

%Using the colon:

1:5 %runs numbers 1 to 5
10:2:20 % this is the form "Starting value: Increments value: Final value", works for both increasing and decreasing values
%A(:,j)	is the jth column of A.
%A(i,:)	is the ith row of A.
%A(:,:)	is the equivalent two-dimensional array. For matrices this is the same as A.
%A(j:k)	is A(j), A(j+1),...,A(k).
%A(:,j:k)	is A(:,j), A(:,j+1),...,A(:,k).
%A(:,:,k)	is the kth page of three-dimensional array A.
%A(i,j,k,:)	is a vector in four-dimensional array A. The vector includes...
%A(i,j,k,1), A(i,j,k,2), A(i,j,k,3), and so on.
%A(:)	is all the elements of A, regarded as a single column. On the left side of an assignment statement, A(:) fills A, preserving its shape from before. In this case, the right side must contain the same number of elements as A.

%Integers:


x = single([5.32 3.47 6.28]) .* 7.5 %converts to single precision number
x = double([5.32 3.47 6.28]) .* 7.5 %converts to double precision number
x = int8([5.32 3.47 6.28]) .* 7.5 %converts to 8-bit signed integer
x = int16([5.32 3.47 6.28]) .* 7.5
x = int32([5.32 3.47 6.28]) .* 7.5
x=uint64([5.32 3.47 6.28]) .* 7.5 %converts to 62-bit unsigned integer

%Functions:

z = num2cell(x) %Converts an array to a cell array with a consistently sized cell (Places each element of x into a seperate cell in z)

%I don't understand intmax() and intmin()

str = 'The range for int8 is:\n\t%d to %d '; %don't get this
sprintf(str, intmin('int8'), intmax('int8'))

str = 'The range for int16 is:\n\t%d to %d ';
sprintf(str, intmin('int16'), intmax('int16'))

str = 'The range for int32 is:\n\t%d to %d ';
sprintf(str, intmin('int32'), intmax('int32'))

str = 'The range for int64 is:\n\t%d to %d ';
sprintf(str, intmin('int64'), intmax('int64'))
 
% displaying the smallest and largest unsigned integer data
str = 'The range for uint8 is:\n\t%d to %d ';
sprintf(str, intmin('uint8'), intmax('uint8'))

str = 'The range for uint16 is:\n\t%d to %d ';
sprintf(str, intmin('uint16'), intmax('uint16'))

str = 'The range for uint32 is:\n\t%d to %d ';
sprintf(str, intmin('uint32'), intmax('uint32'))

str = 'The range for uint64 is:\n\t%d to %d ';
sprintf(str, intmin('uint64'), intmax('uint64'))

%I don't really understand realmax() and realmin()

% displaying the smallest and largest single-precision ...
% floating point number (don't really get floating point numbers)
str = 'The range for single is:\n\t%g to %g and\n\t %g to  %g';
sprintf(str, -realmax('single'), -realmin('single'), ...
   realmin('single'), realmax('single'))

% displaying the smallest and largest double-precision 
% floating point number
str = 'The range for double is:\n\t%g to %g and\n\t %g to  %g';
sprintf(str, -realmax('double'), -realmin('double'), ...
   realmin('double'), realmax('double'))


%Strings (just character arrays essentially):

my_string=('tutorial')
whos

string_to_integer = uint8(my_string)        % 8-bit ascii values (use uit8/uit16 to convert characters back to num. integers)
string_to_character= char(string_to_integer)  %"char" function converts the integer vector back to characters
string_16bit = uint16(my_string)       % 16-bit ascii values
str_back_to_char = char(string_16bit)

%Rectangular Character Array:

%Use the concatenation operator [] and separate each row with a semicolon (;). In this method each row must contain the same number of characters. For strings with different lengths, add space characters to get the equal lengths as needed.
%Or: Use the "char" function. If the strings are of different lengths, char automatically pads the shorter strings with trailing blanks so that each row has the same number of characters.

Teacher_Profile = ['Mrs Barton        ';...
                   'Head of St.Georges';...
                   'Geography teacher ']
                
Teacher_Profile = char('Mr Daish', 'Head of PE', 'PE teacher') %This is the easier way to do it, generally

name =     'Zara Ali                             '; %for combining strings horizontally, use either the concatenation operator [] and seperate each row with a semicolon (;) and this method preserves trailing spaces - or use "strcat", the string concatenation function, which automatically removes trailing spaces
position = 'Sr. Surgeon                          '; 
worksAt =  'R N Tagore Cardiology Research Center';
profile = [name ', ' position ', ' worksAt]
profile = strcat(name, ', ', position, ', ', worksAt)

%Combining strings into a cell array

%MATLAB cell array can hold different sizes and types of data in an array. Cell arrays provide a more flexible way to store strings of varying length.
%The "cellstr" function converts a character array into a cell array of strings.

%Function - Group of statements that together perform a task:

I=[1 2 3; 4 5 6]
J=[2 3 4; 5 6 7]
I.*J



%The "clc" command clears the screen entirely
%The "clear" command clears all the values of previous variables and functions, etc. 
%Therefore, it's always good to start a new piece of code with 'clear' and 'clc'

%Use square brackets for writing a matrix

%mod(a,m) gives you the remainder after dividing a by m

mod(9,3)
mod(10,3)

%struct=structural array

mystruct.name='Harry'
mystruct.age=18
B=mystruct
isfield(mystruct,'age') %is 'age' a field within my struct, yes
isfield(mystruct,'height') %is 'height' a field within my struct, no

%Plotting data:

y=[1,1,2,3,5,8,13,21]
x=[3,4,6,7,5,2,5,1,9]
% plot(x,y); this doesn't seem to be working for some reason
title('A plot of x against y') %gives a title to the plot
xlabel('Label for x-axis')
ylabel('Label for y-axis')

%B=arrayfun(Intensity2Temp,I) research this
%x=linspace(0:100:200) In the form of: (starting point:end point:number of intervals) research this

%hist creates a histogram
%pie creates a pie chart
%scatter creates a scatter diagram

M=[1 2 3; 5 3 1; 9 2 7]
surf(M) %Gives a 3-D diagram of the matrix

%contour(M) %Gives like a 2-D representation of the 3-D matrix, red = really high values, blue = really low values (in negatives, blue is large, red is small)

J='Harry'
K='18'
fprintf('Well Hello There, %s\n', J)
fprintf('I am %d\n',K, 'Years Old') %Look at command window - I don't know why this is happening

M=[2,3;3,4]
A=mean(M,'all')

%You can never put anything after any functions in a script, otherwise you will get an error. eg: Imshow(T) must come after 'T' is defined, but before all of the functions.

%dir IR images 3ms\layer_11_1561631723710 %"dir name" lists files and I=importdata(IR images 3ms\layer_11_1561631723710_3772), folders that match "name". When "name" is a folder, "dir" lists the contents of the folder. Specify "name" using absolute or relative path names. The name argument can include the * wildcard in the file name, and both the * and the ** wildcard in the path name. Characters next to a ** wildcard must be file separators. (I don't really get the last 2 sentances.)

%'num2str' converts a number to a string (see Video_Of_Frames2 to find an example of its possible uses.)

%"figure" creates a new figure window using default property values. The resulting figure is the current figure.

%to get crosses at all the data points on a plot/graph, you need to add a ",'-x'" and this makes your data points more easy to see. eg: plot(x,y,'-x')

%The "hold" function determines whether new graphics objects are added to the graph/plot or replace objects in the graph/plot. eg: "hold on" retains the current plot and certain axes properties so that subsequent graphing commands add to the existing graph. "hold off" resets axes properties to their defaults before drawing new plots. "hold off" is the default setting, ie: you must set hold to "on", otherwise it will remain "off". "hold" toggles the hold state between adding to the graph and replacing the graph.

%S=importdata(filename); does the same thing as "imread" just without you having to translate all of your data into the "double" data type.

%"[files, path] = uigetfile({'*.tif'},'Multiselect','on');" %Must use the squigly brackets "{}" when using "uigetfile" - this is an alternative to the "num2str" method.
%for n=1:length(files) %or n=3772:4566 for matching with line 11.
    %filename = [path files{n}];
    %etc
%Use "!git" to test if you can move this code directly into GitHub.

%git init initializes a brand new Git repository and begins tracking an existing directory. It adds a hidden subfolder within the existing directory that houses the internal data structure required for version control.

%git clone creates a local copy of a project that already exists remotely. The clone includes all the project’s files, history, and branches.

%git add stages a change. Git tracks changes to a developer’s codebase, but it’s necessary to stage and take a snapshot of the changes to include them in the project’s history. This command performs staging, the first part of that two-step process. Any changes that are staged will become a part of the next snapshot and a part of the project’s history. Staging and committing separately gives developers complete control over the history of their project without changing how they code and work.

%git commit saves the snapshot to the project history and completes the change-tracking process. In short, a commit functions like taking a photo. Anything that’s been staged with git add will become a part of the snapshot with git commit.

%git status shows the status of changes as untracked, modified, or staged.

%git branch shows the branches being worked on locally.

%git merge merges lines of development together. This command is typically used to combine changes made on two distinct branches. For example, a developer would merge when they want to combine changes from a feature branch into the main branch for deployment.

%git pull updates the local line of development with updates from its remote counterpart. Developers use this command if a teammate has made commits to a branch on a remote, and they would like to reflect those changes in their local environment.

%git push updates the remote repository with any commits made locally to a branch.

%https://uk.mathworks.com/help/matlab/matlab_prog/add-folder-to-source-control.html
%https://uk.mathworks.com/help/matlab/matlab_prog/use-source-control-with-projects.html
%https://uk.mathworks.com/help/simulink/ug/push-and-fetch-files-with-git.html
%https://uk.mathworks.com/help/matlab/matlab_prog/set-up-git-source-control.html
%https://blogs.mathworks.com/community/2014/10/20/matlab-and-git/
%https://www.youtube.com/watch?v=0fKg7e37bQE
