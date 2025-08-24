### 1.Bit++

The classic programming language of Bitland is Bit++. This language is so peculiar and complicated.

The language is that peculiar as it has exactly one variable, called x. Also, there are two operations:

Operation ++ increases the value of variable x by 1.
Operation -- decreases the value of variable x by 1.
A statement in language Bit++ is a sequence, consisting of exactly one operation and one variable x. The statement is written without spaces, that is, it can only contain characters "+", "-", "X". Executing a statement means applying the operation it contains.

A programme in Bit++ is a sequence of statements, each of them needs to be executed. Executing a programme means executing all the statements it contains.

You're given a programme in language Bit++. The initial value of x is 0. Execute the programme and find its final value (the value of the variable when this programme is executed).

Input
The first line contains a single integer n (1 ≤ n ≤ 150) — the number of statements in the programme.

Next n lines contain a statement each. Each statement contains exactly one operation (++ or --) and exactly one variable x (denoted as letter «X»). Thus, there are no empty statements. The operation and the variable can be written in any order.

Output
Print a single integer — the final value of x.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    int x=0;
    for(int i=0;i<n;i++){
        string op;
        cin>>op;
        if((op[0]=='X' && op[1]=='+') || op[0]=='+')
        x++;
        else
        x--;
    }
    cout<<x<<endl;
}
```

### 2. Chewbaсca and Number

Luke Skywalker gave Chewbacca an integer number x. Chewbacca isn't good at numbers but he loves inverting digits in them. Inverting digit t means replacing it with digit 9 - t.

Help Chewbacca to transform the initial number x to the minimum possible positive number by inverting some (possibly, zero) digits. The decimal representation of the final number shouldn't start with a zero.

Input
The first line contains a single integer x (1 ≤ x ≤ 1018) — the number that Luke Skywalker gave to Chewbacca.

Output
Print the minimum possible positive number that Chewbacca can obtain after inverting some digits. The number shouldn't contain leading zeroes.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string x,x1;
    cin>>x;
    for(int i=0;i<x.size();i++){
        int dig=x[i]-'0';
        if(dig==9 && i==0)
        {
            x1+=(dig+'0');
            continue;
        }
        if(dig>9-dig){
            x1+=(9-dig+'0');
        }else{
            x1+=(dig+'0');
        }
    }
    cout<<x1<<endl;
}
```

### 3. Beautiful Matrix

You've got a 5 × 5 matrix, consisting of 24 zeroes and a single number one. Let's index the matrix rows by numbers from 1 to 5 from top to bottom, let's index the matrix columns by numbers from 1 to 5 from left to right. In one move, you are allowed to apply one of the two following transformations to the matrix:

Swap two neighboring matrix rows, that is, rows with indexes i and i + 1 for some integer i (1 ≤ i < 5).
Swap two neighboring matrix columns, that is, columns with indexes j and j + 1 for some integer j (1 ≤ j < 5).
You think that a matrix looks beautiful, if the single number one of the matrix is located in its middle (in the cell that is on the intersection of the third row and the third column). Count the minimum number of moves needed to make the matrix beautiful.

Input
The input consists of five lines, each line contains five integers: the j-th integer in the i-th line of the input represents the element of the matrix that is located on the intersection of the i-th row and the j-th column. It is guaranteed that the matrix consists of 24 zeroes and a single number one.

Output
Print a single integer — the minimum number of moves needed to make the matrix beautiful.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int x,y;
    for(int i=0;i<5;i++){
        for(int j=0;j<5;j++){
            char c;
            cin>>c;
            if(c=='1'){
                x=i;
                y=j;
            }
        }
    }
    cout<<(abs(x-2)+abs(y-2))<<endl;
}
```

### 4. Soft Drinking

This winter is so cold in Nvodsk! A group of n friends decided to buy k bottles of a soft drink called "Take-It-Light" to warm up a bit. Each bottle has l milliliters of the drink. Also they bought c limes and cut each of them into d slices. After that they found p grams of salt.

To make a toast, each friend needs nl milliliters of the drink, a slice of lime and np grams of salt. The friends want to make as many toasts as they can, provided they all drink the same amount. How many toasts can each friend make?

Input
The first and only line contains positive integers n, k, l, c, d, p, nl, np, not exceeding 1000 and no less than 1. The numbers are separated by exactly one space.

Output
Print a single integer — the number of toasts each friend can make.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n,k,l,c,d,p,nl,np;
    cin>>n>>k>>l>>c>>d>>p>>nl>>np;
    cout<<min({k*l/nl,c*d,p/np})/n;
}
```

### 5. The New Year: Meeting Friends

There are three friend living on the straight line Ox in Lineland. The first friend lives at the point x1, the second friend lives at the point x2, and the third friend lives at the point x3. They plan to celebrate the New Year together, so they need to meet at one point. What is the minimum total distance they have to travel in order to meet at some point and celebrate the New Year?

It's guaranteed that the optimal answer is always integer.

Input
The first line of the input contains three distinct integers x1, x2 and x3 (1 ≤ x1, x2, x3 ≤ 100) — the coordinates of the houses of the first, the second and the third friends respectively.

Output
Print one integer — the minimum total distance the friends need to travel in order to meet together.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    vector<int>x(3);
    for(auto &i:x)
    cin>>i;
    sort(x.begin(),x.end());
    int dist=0;
    for(auto ele:x)
    dist+=abs(ele-x[1]);
    cout<<dist<<endl;
}
```

### 6. Sum of Round Numbers

A positive (strictly greater than zero) integer is called round if it is of the form d00...0. In other words, a positive integer is round if all its digits except the leftmost (most significant) are equal to zero. In particular, all numbers from 1
 to 9
 (inclusive) are round.

For example, the following numbers are round: 4000
, 1
, 9
, 800
, 90
. The following numbers are not round: 110
, 707
, 222
, 1001
.

You are given a positive integer n
 (1≤n≤104
). Represent the number n
 as a sum of round numbers using the minimum number of summands (addends). In other words, you need to represent the given number n
 as a sum of the least number of terms, each of which is a round number.

Input
The first line contains an integer t
 (1≤t≤104
) — the number of test cases in the input. Then t
 test cases follow.

Each test case is a line containing an integer n
 (1≤n≤104
).

Output
Print t
 answers to the test cases. Each answer must begin with an integer k
 — the minimum number of summands. Next, k
 terms must follow, each of which is a round number, and their sum is n
. The terms can be printed in any order. If there are several answers, print any of them.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        int k=0;
        vector<int>addends;
        int zc=1;
        while(n>0){
            int dig=n%10;
            if(dig!=0)
            {k++;addends.push_back(dig*zc);}
            n/=10;
            zc*=10;
        }
        cout<<k<<endl;
        for(auto ele:addends)
        cout<<ele<<" ";
        cout<<endl;
    }
}
```

### 7. Fox And Snake

Fox Ciel starts to learn programming. The first task is drawing a fox! However, that turns out to be too hard for a beginner, so she decides to draw a snake instead.

A snake is a pattern on a n by m table. Denote c-th cell of r-th row as (r, c). The tail of the snake is located at (1, 1), then it's body extends to (1, m), then goes down 2 rows to (3, m), then goes left to (3, 1) and so on.

Your task is to draw this snake for Fox Ciel: the empty cells should be represented as dot characters ('.') and the snake cells should be filled with number signs ('#').

Consider sample tests in order to understand the snake pattern.

Input
The only line contains two integers: n and m (3 ≤ n, m ≤ 50).

n is an odd number.

Output
Output n lines. Each line should contain a string consisting of m characters. Do not output spaces.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n,m;
    cin>>n>>m;
    vector<vector<char>>mat(n,vector<char>(m,'.'));
    int i=0,j=0;
    while(i<n-1){
        for(j=0;j<m-1;j++)
        mat[i][j]='#';
        int row=i;
        for(i=row;i<min(row+3,n)-1;i++)
            mat[i][j]='#';
        for(j=m-1;j>0;j--)
        mat[i][j]='#';
        row=i;
        for(i=row;i<min(row+3,n)-1;i++)
        mat[i][j]='#';
    }
    for(j=0;j<m;j++)
        mat[i][j]='#';
    for(auto v:mat){
        for(auto ele:v)
        cout<<ele;
        cout<<endl;
    }
}
```

### 8. Anton and Polyhedrons

Anton's favourite geometric figures are regular polyhedrons. Note that there are five kinds of regular polyhedrons:

Tetrahedron. Tetrahedron has 4 triangular faces.
Cube. Cube has 6 square faces.
Octahedron. Octahedron has 8 triangular faces.
Dodecahedron. Dodecahedron has 12 pentagonal faces.
Icosahedron. Icosahedron has 20 triangular faces.
All five kinds of polyhedrons are shown on the picture below:


Anton has a collection of n polyhedrons. One day he decided to know, how many faces his polyhedrons have in total. Help Anton and find this number!

Input
The first line of the input contains a single integer n (1 ≤ n ≤ 200 000) — the number of polyhedrons in Anton's collection.

Each of the following n lines of the input contains a string si — the name of the i-th polyhedron in Anton's collection. The string can look like this:

"Tetrahedron" (without quotes), if the i-th polyhedron in Anton's collection is a tetrahedron.
"Cube" (without quotes), if the i-th polyhedron in Anton's collection is a cube.
"Octahedron" (without quotes), if the i-th polyhedron in Anton's collection is an octahedron.
"Dodecahedron" (without quotes), if the i-th polyhedron in Anton's collection is a dodecahedron.
"Icosahedron" (without quotes), if the i-th polyhedron in Anton's collection is an icosahedron.
Output
Output one number — the total number of faces in all the polyhedrons in Anton's collection.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    int sum=0;
    for(int i=0;i<n;i++){
        string shape;
        cin>>shape;
        if(shape=="Cube")
        sum+=6;
        else if(shape=="Tetrahedron")
        sum+=4;
        else if(shape=="Octahedron")
        sum+=8;
        else if(shape=="Dodecahedron")
        sum+=12;
        else
        sum+=20;
    }
    cout<<sum<<endl;
}
```

### 9. Arrival of the General

A Ministry for Defense sent a general to inspect the Super Secret Military Squad under the command of the Colonel SuperDuper. Having learned the news, the colonel ordered to all n squad soldiers to line up on the parade ground.

By the military charter the soldiers should stand in the order of non-increasing of their height. But as there's virtually no time to do that, the soldiers lined up in the arbitrary order. However, the general is rather short-sighted and he thinks that the soldiers lined up correctly if the first soldier in the line has the maximum height and the last soldier has the minimum height. Please note that the way other solders are positioned does not matter, including the case when there are several soldiers whose height is maximum or minimum. Only the heights of the first and the last soldier are important.

For example, the general considers the sequence of heights (4, 3, 4, 2, 1, 1) correct and the sequence (4, 3, 1, 2, 2) wrong.

Within one second the colonel can swap any two neighboring soldiers. Help him count the minimum time needed to form a line-up which the general will consider correct.

Input
The first input line contains the only integer n (2 ≤ n ≤ 100) which represents the number of soldiers in the line. The second line contains integers a1, a2, ..., an (1 ≤ ai ≤ 100) the values of the soldiers' heights in the order of soldiers' heights' increasing in the order from the beginning of the line to its end. The numbers are space-separated. Numbers a1, a2, ..., an are not necessarily different.

Output
Print the only integer — the minimum number of seconds the colonel will need to form a line-up the general will like.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>v(n);
    for(auto &i:v)
    cin>>i;
    int mino=*min_element(v.begin(),v.end());
    int maxo=*max_element(v.begin(),v.end());
    int minidx=-1;
    for(int i=n-1;i>=0;i--){
        if(v[i]==mino)
        {
            minidx=i;
            break;
        }
    }
    int maxidx=-1;
    for(int i=0;i<n;i++){
        if(v[i]==maxo){
            maxidx=i;
            break;
        }
    }
    if(minidx>maxidx)
    cout<<(n-minidx-1)+maxidx<<endl;
    else
    cout<<(n-minidx-2)+maxidx<<endl;
}
```

### 10. In Search of an Easy Problem

When preparing a tournament, Codeforces coordinators try treir best to make the first problem as easy as possible. This time the coordinator had chosen some problem and asked n
 people about their opinions. Each person answered whether this problem is easy or hard.

If at least one of these n
 people has answered that the problem is hard, the coordinator decides to change the problem. For the given responses, check if the problem is easy enough.

Input
The first line contains a single integer n
 (1≤n≤100
) — the number of people who were asked to give their opinions.

The second line contains n
 integers, each integer is either 0
 or 1
. If i
-th integer is 0
, then i
-th person thinks that the problem is easy; if it is 1
, then i
-th person thinks that the problem is hard.

Output
Print one word: "EASY" if the problem is easy according to all responses, or "HARD" if there is at least one person who thinks the problem is hard.

You may print every letter in any register: "EASY", "easy", "EaSY" and "eAsY" all will be processed correctly.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>v(n);
    string res="EASY";
    for(auto &i:v)
    {
        cin>>i;
        if(i==1)
        res="HARD";
    }
    cout<<res<<endl;
}
```

### 11. Presents

Little Petya very much likes gifts. Recently he has received a new laptop as a New Year gift from his mother. He immediately decided to give it to somebody else as what can be more pleasant than giving somebody gifts. And on this occasion he organized a New Year party at his place and invited n his friends there.

If there's one thing Petya likes more that receiving gifts, that's watching others giving gifts to somebody else. Thus, he safely hid the laptop until the next New Year and made up his mind to watch his friends exchanging gifts while he does not participate in the process. He numbered all his friends with integers from 1 to n. Petya remembered that a friend number i gave a gift to a friend number pi. He also remembered that each of his friends received exactly one gift.

Now Petya wants to know for each friend i the number of a friend who has given him a gift.

Input
The first line contains one integer n (1 ≤ n ≤ 100) — the quantity of friends Petya invited to the party. The second line contains n space-separated integers: the i-th number is pi — the number of a friend who gave a gift to friend number i. It is guaranteed that each friend received exactly one gift. It is possible that some friends do not share Petya's ideas of giving gifts to somebody else. Those friends gave the gifts to themselves.

Output
Print n space-separated integers: the i-th number should equal the number of the friend who gave a gift to friend number i.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>v(n);
    map<int,int>mp;
    for(int i=0;i<n;i++){
        cin>>v[i];
        mp[v[i]]=i+1;
    }
    for(int i=1;i<=n;i++)
        cout<<mp[i]<<" ";
}
```

### 12. Nearly Lucky Number

Petya loves lucky numbers. We all know that lucky numbers are the positive integers whose decimal representations contain only the lucky digits 4 and 7. For example, numbers 47, 744, 4 are lucky and 5, 17, 467 are not.

Unfortunately, not all numbers are lucky. Petya calls a number nearly lucky if the number of lucky digits in it is a lucky number. He wonders whether number n is a nearly lucky number.

Input
The only line contains an integer n (1 ≤ n ≤ 1018).

Please do not use the %lld specificator to read or write 64-bit numbers in С++. It is preferred to use the cin, cout streams or the %I64d specificator.

Output
Print on the single line "YES" if n is a nearly lucky number. Otherwise, print "NO" (without the quotes).

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string n;
    cin>>n;
    int cnt=0;
    for(int i=0;i<n.size();i++){
        if(n[i]=='4' || n[i]=='7')
        cnt++;
    }
    if(cnt==4 || cnt==7)
    cout<<"YES";
    else
    cout<<"NO";
}
```

### 13. Tram

Linear Kingdom has exactly one tram line. It has n stops, numbered from 1 to n in the order of tram's movement. At the i-th stop ai passengers exit the tram, while bi passengers enter it. The tram is empty before it arrives at the first stop. Also, when the tram arrives at the last stop, all passengers exit so that it becomes empty.

Your task is to calculate the tram's minimum capacity such that the number of people inside the tram at any time never exceeds this capacity. Note that at each stop all exiting passengers exit before any entering passenger enters the tram.

Input
The first line contains a single number n (2 ≤ n ≤ 1000) — the number of the tram's stops.

Then n lines follow, each contains two integers ai and bi (0 ≤ ai, bi ≤ 1000) — the number of passengers that exits the tram at the i-th stop, and the number of passengers that enter the tram at the i-th stop. The stops are given from the first to the last stop in the order of tram's movement.

The number of people who exit at a given stop does not exceed the total number of people in the tram immediately before it arrives at the stop. More formally, . This particularly means that a1 = 0.
At the last stop, all the passengers exit the tram and it becomes empty. More formally, .
No passenger will enter the train at the last stop. That is, bn = 0.
Output
Print a single integer denoting the minimum possible capacity of the tram (0 is allowed).

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    int maxcap=0,cap=0;
    for(int i=0;i<n;i++){
        int a,b;
        cin>>a>>b;
        cap+=b-a;
        maxcap=max(maxcap,cap);
    }
    cout<<maxcap<<endl;
}
```
