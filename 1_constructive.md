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

### 14. Wrong Subtraction

Little girl Tanya is learning how to decrease a number by one, but she does it wrong with a number consisting of two or more digits. Tanya subtracts one from a number by the following algorithm:

if the last digit of the number is non-zero, she decreases the number by one;
if the last digit of the number is zero, she divides the number by 10 (i.e. removes the last digit).
You are given an integer number n
. Tanya will subtract one from it k
 times. Your task is to print the result after all k
 subtractions.

It is guaranteed that the result will be positive integer number.

Input
The first line of the input contains two integer numbers n
 and k
 (2≤n≤109
, 1≤k≤50
) — the number from which Tanya will subtract and the number of subtractions correspondingly.

Output
Print one integer number — the result of the decreasing n
 by one k
 times.

It is guaranteed that the result will be positive integer number.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n,k;
    cin>>n>>k;
    while(k--){
        int dig=n%10;
        if(dig!=0)
        n--;
        else
        n/=10;
    }
    cout<<n<<endl;
}
```

### 15. Soldier and Bananas

A soldier wants to buy w bananas in the shop. He has to pay k dollars for the first banana, 2k dollars for the second one and so on (in other words, he has to pay i·k dollars for the i-th banana).

He has n dollars. How many dollars does he have to borrow from his friend soldier to buy w bananas?

Input
The first line contains three positive integers k, n, w (1  ≤  k, w  ≤  1000, 0 ≤ n ≤ 109), the cost of the first banana, initial number of dollars the soldier has and number of bananas he wants.

Output
Output one integer — the amount of dollars that the soldier must borrow from his friend. If he doesn't have to borrow money, output 0.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int k,n,w;
    cin>>k>>n>>w;
    int cost=0;
    for(int i=1;i<=w;i++)
    cost+=i*k;
    if(cost>n)
    cout<<cost-n<<endl;
    else
    cout<<0<<endl;
}
```

### 16. Bear and Big Brother

Bear Limak wants to become the largest of bears, or at least to become larger than his brother Bob.

Right now, Limak and Bob weigh a and b respectively. It's guaranteed that Limak's weight is smaller than or equal to his brother's weight.

Limak eats a lot and his weight is tripled after every year, while Bob's weight is doubled after every year.

After how many full years will Limak become strictly larger (strictly heavier) than Bob?

Input
The only line of the input contains two integers a and b (1 ≤ a ≤ b ≤ 10) — the weight of Limak and the weight of Bob respectively.

Output
Print one integer, denoting the integer number of years after which Limak will become strictly larger than Bob.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int a,b;
    cin>>a>>b;
    int cnt=0;
    while(a<=b){
        a*=3;
        b*=2;
        cnt++;
    }
    cout<<cnt<<endl;
}
```

### 17. Boy or Girl

Those days, many boys use beautiful girls' photos as avatars in forums. So it is pretty hard to tell the gender of a user at the first glance. Last year, our hero went to a forum and had a nice chat with a beauty (he thought so). After that they talked very often and eventually they became a couple in the network.

But yesterday, he came to see "her" in the real world and found out "she" is actually a very strong man! Our hero is very sad and he is too tired to love again now. So he came up with a way to recognize users' genders by their user names.

This is his method: if the number of distinct characters in one's user name is odd, then he is a male, otherwise she is a female. You are given the string that denotes the user name, please help our hero to determine the gender of this user by his method.

Input
The first line contains a non-empty string, that contains only lowercase English letters — the user name. This string contains at most 100 letters.

Output
If it is a female by our hero's method, print "CHAT WITH HER!" (without the quotes), otherwise, print "IGNORE HIM!" (without the quotes).

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string s;
    cin>>s;
    set<char>seto;
    for(auto c:s)
    seto.insert(c);
    if(seto.size()%2!=0)
    cout<<"IGNORE HIM!";
    else
    cout<<"CHAT WITH HER!";
}
```

### 18. Word Capitalization

Capitalization is writing a word with its first letter as a capital letter. Your task is to capitalize the given word.

Note, that during capitalization all the letters except the first one remains unchanged.

Input
A single line contains a non-empty word. This word consists of lowercase and uppercase English letters. The length of the word will not exceed 103.

Output
Output the given word after capitalization.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string s;
    cin>>s;
    if(s[0]>='a' && s[0]<='z')
    s[0]=(char)(s[0]-32);
    cout<<s<<endl;
}
```

### 19 Helpful Maths

Xenia the beginner mathematician is a third year student at elementary school. She is now learning the addition operation.

The teacher has written down the sum of multiple numbers. Pupils should calculate the sum. To make the calculation easier, the sum only contains numbers 1, 2 and 3. Still, that isn't enough for Xenia. She is only beginning to count, so she can calculate a sum only if the summands follow in non-decreasing order. For example, she can't calculate sum 1+3+2+1 but she can calculate sums 1+1+2 and 3+3.

You've got the sum that was written on the board. Rearrange the summans and print the sum in such a way that Xenia can calculate the sum.

Input
The first line contains a non-empty string s — the sum Xenia needs to count. String s contains no spaces. It only contains digits and characters "+". Besides, string s is a correct sum of numbers 1, 2 and 3. String s is at most 100 characters long.

Output
Print the new sum that Xenia can count.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string s;
    cin>>s;
    vector<char>v;
    for(int i=0;i<s.size();i+=2)
    v.push_back(s[i]);
    sort(v.begin(),v.end());
    int k=0;
    for(int i=0;i<s.size();i+=2)
    s[i]=v[k++];
    cout<<s<<endl;
}
```

### 20 C+=

Leo has developed a new programming language C+=. In C+=, integer variables can only be changed with a "+=" operation that adds the right-hand side value to the left-hand side variable. For example, performing "a += b" when a = 2
, b = 3
 changes the value of a to 5
 (the value of b does not change).

In a prototype program Leo has two integer variables a and b, initialized with some positive values. He can perform any number of operations "a += b" or "b += a". Leo wants to test handling large integers, so he wants to make the value of either a or b strictly greater than a given value n
. What is the smallest number of operations he has to perform?

Input
The first line contains a single integer T
 (1≤T≤100
) — the number of test cases.

Each of the following T
 lines describes a single test case, and contains three integers a,b,n
 (1≤a,b≤n≤109
) — initial values of a and b, and the value one of the variables has to exceed, respectively.

Output
For each test case print a single integer — the smallest number of operations needed. Separate answers with line breaks.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int a,b,n;
        cin>>a>>b>>n;
        if(a>n || b>n)
        cout<<0<<endl;
        else
        {
            int cnt=0;
            priority_queue<int,vector<int>>pq;
            pq.push(a);
            pq.push(b);
            while(pq.top()<=n){
                int num1=pq.top();
                pq.pop();
                int num2=pq.top();
                pq.pop();
                pq.push(max(num1,num2));
                pq.push(num1+num2);
                cnt++;
            }
            cout<<cnt<<endl;
        }
    }
}
```

### 21 Maximum Increase

You are given array consisting of n integers. Your task is to find the maximum length of an increasing subarray of the given array.

A subarray is the sequence of consecutive elements of the array. Subarray is called increasing if each element of this subarray strictly greater than previous.

Input
The first line contains single positive integer n (1 ≤ n ≤ 105) — the number of integers.

The second line contains n positive integers a1, a2, ..., an (1 ≤ ai ≤ 109).

Output
Print the maximum length of an increasing subarray of the given array.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>a(n);
    for(auto &i:a)
    cin>>i;
    int temp=1,maxlen=1;
    for(int i=1;i<n;i++){
        if(a[i-1]<a[i])
            temp++;
        else    
            temp=1;
        maxlen=max(maxlen,temp);
    }
    cout<<maxlen<<endl;
}
```

### 22 Gennady and a Card Game

Gennady owns a small hotel in the countryside where he lives a peaceful life. He loves to take long walks, watch sunsets and play cards with tourists staying in his hotel. His favorite game is called "Mau-Mau".

To play Mau-Mau, you need a pack of 52
 cards. Each card has a suit (Diamonds — D, Clubs — C, Spades — S, or Hearts — H), and a rank (2, 3, 4, 5, 6, 7, 8, 9, T, J, Q, K, or A).

At the start of the game, there is one card on the table and you have five cards in your hand. You can play a card from your hand if and only if it has the same rank or the same suit as the card on the table.

In order to check if you'd be a good playing partner, Gennady has prepared a task for you. Given the card on the table and five cards in your hand, check if you can play at least one card.

Input
The first line of the input contains one string which describes the card on the table. The second line contains five strings which describe the cards in your hand.

Each string is two characters long. The first character denotes the rank and belongs to the set {2,3,4,5,6,7,8,9,T,J,Q,K,A}
. The second character denotes the suit and belongs to the set {D,C,S,H}
.

All the cards in the input are different.

Output
If it is possible to play a card from your hand, print one word "YES". Otherwise, print "NO".

You can print each letter in any case (upper or lower).

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string table;
    cin>>table;
    int ideal_rank=table[0];
    int ideal_suit=table[1];
    vector<string>v(5);
    bool chk=false;
    for(auto &i:v){
        cin>>i;
        if(i[0]==ideal_rank)
        chk=true;
        else if(i[1]==ideal_suit)
        chk=true;
    }
    if(chk)
    cout<<"YES";
    else
    cout<<"NO";
}
```

### 23 Vanya and Cubes

Vanya got n cubes. He decided to build a pyramid from them. Vanya wants to build the pyramid as follows: the top level of the pyramid must consist of 1 cube, the second level must consist of 1 + 2 = 3 cubes, the third level must have 1 + 2 + 3 = 6 cubes, and so on. Thus, the i-th level of the pyramid must have 1 + 2 + ... + (i - 1) + i cubes.

Vanya wants to know what is the maximum height of the pyramid that he can make using the given cubes.

Input
The first line contains integer n (1 ≤ n ≤ 104) — the number of cubes given to Vanya.

Output
Print the maximum possible height of the pyramid in the single line.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    int cnt=0;
    int sum=0;
    while(sum<n){
        cnt++;
        sum+=cnt*(cnt+1)/2;
    }
    if(sum>n)
    cout<<cnt-1<<endl;
    else
    cout<<cnt<<endl;
}
```

### 24 Boring Apartments

There is a building consisting of 10 000
 apartments numbered from 1
 to 10 000
, inclusive.

Call an apartment boring, if its number consists of the same digit. Examples of boring apartments are 11,2,777,9999
 and so on.

Our character is a troublemaker, and he calls the intercoms of all boring apartments, till someone answers the call, in the following order:

First he calls all apartments consisting of digit 1
, in increasing order (1,11,111,1111
).
Next he calls all apartments consisting of digit 2
, in increasing order (2,22,222,2222
)
And so on.
The resident of the boring apartment x
 answers the call, and our character stops calling anyone further.

Our character wants to know how many digits he pressed in total and your task is to help him to count the total number of keypresses.

For example, if the resident of boring apartment 22
 answered, then our character called apartments with numbers 1,11,111,1111,2,22
 and the total number of digits he pressed is 1+2+3+4+1+2=13
.

You have to answer t
 independent test cases.

Input
The first line of the input contains one integer t
 (1≤t≤36
) — the number of test cases.

The only line of the test case contains one integer x
 (1≤x≤9999
) — the apartment number of the resident who answered the call. It is guaranteed that x
 consists of the same digit.

Output
For each test case, print the answer: how many digits our character pressed in total.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int x;
        cin>>x;
        int ans=0;
        for(int dig=1;dig<=9;dig++){
            if(dig<(x%10))
                ans+=10;
            else{
                int sz=to_string(x).size();
                if(sz==1)
                ans++;
                else if(sz==2)
                ans+=3;
                else if(sz==3)
                ans+=6;
                else
                ans+=10;
                break;
            }
        }
        cout<<ans<<endl;
    }
}
```

### 25 Erasing Zeroes

You are given a string s
. Each character is either 0 or 1.

You want all 1's in the string to form a contiguous subsegment. For example, if the string is 0, 1, 00111 or 01111100, then all 1's form a contiguous subsegment, and if the string is 0101, 100001 or 11111111111101, then this condition is not met.

You may erase some (possibly none) 0's from the string. What is the minimum number of 0's that you have to erase?

Input
The first line contains one integer t
 (1≤t≤100
) — the number of test cases.

Then t
 lines follow, each representing a test case. Each line contains one string s
 (1≤|s|≤100
); each character of s
 is either 0 or 1.

Output
Print t
 integers, where the i
-th integer is the answer to the i
-th testcase (the minimum number of 0's that you have to erase from s
).

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        string s;
        cin>>s;
        bool chk1=false,chk2=true;
        int cnt=0,res=0;
        for(int i=0;i<s.size();i++){
            if(s[i]=='1' && chk1==false)
                chk1=true;
            if(s[i]=='0' && chk1==true){
                chk2=true;
                cnt++;
            }
            if(s[i]=='1' && chk1==true && chk2==true)
            {
                chk2=false;
                res+=cnt;
                cnt=0;
            }
        }
        cout<<res<<endl;
    }
}
```

### 26 Repeating Cipher

Polycarp loves ciphers. He has invented his own cipher called repeating.

Repeating cipher is used for strings. To encrypt the string s=s1s2…sm
 (1≤m≤10
), Polycarp uses the following algorithm:

he writes down s1
 ones,
he writes down s2
 twice,
he writes down s3
 three times,
...
he writes down sm
 m
 times.
For example, if s
="bab" the process is: "b" →
 "baa" →
 "baabbb". So the encrypted s
="bab" is "baabbb".

Given string t
 — the result of encryption of some string s
. Your task is to decrypt it, i. e. find the string s
.

Input
The first line contains integer n
 (1≤n≤55
) — the length of the encrypted string. The second line of the input contains t
 — the result of encryption of some string s
. It contains only lowercase Latin letters. The length of t
 is exactly n
.

It is guaranteed that the answer to the test exists.

Output
Print such string s
 that after encryption it equals t
.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    string t,res;
    cin>>t;
    int cnt=0;
    for(int i=0;i<n;i+=cnt){
        cnt++;
        res+=t[i];
    }
    cout<<res<<endl;
}
```

### 27 Fix You

Consider a conveyor belt represented using a grid consisting of n
 rows and m
 columns. The cell in the i
-th row from the top and the j
-th column from the left is labelled (i,j)
.

Every cell, except (n,m)
, has a direction R (Right) or D (Down) assigned to it. If the cell (i,j)
 is assigned direction R, any luggage kept on that will move to the cell (i,j+1)
. Similarly, if the cell (i,j)
 is assigned direction D, any luggage kept on that will move to the cell (i+1,j)
. If at any moment, the luggage moves out of the grid, it is considered to be lost.

There is a counter at the cell (n,m)
 from where all luggage is picked. A conveyor belt is called functional if and only if any luggage reaches the counter regardless of which cell it is placed in initially. More formally, for every cell (i,j)
, any luggage placed in this cell should eventually end up in the cell (n,m)
.

This may not hold initially; you are, however, allowed to change the directions of some cells to make the conveyor belt functional. Please determine the minimum amount of cells you have to change.

Please note that it is always possible to make any conveyor belt functional by changing the directions of some set of cells.

Input
Each test contains multiple test cases. The first line contains the number of test cases t
 (1≤t≤10
). Description of the test cases follows.

The first line of each test case contains two integers n,m
 (1≤n≤100
, 1≤m≤100
)  — the number of rows and columns, respectively.

The following n
 lines each contain m
 characters. The j
-th character in the i
-th line, ai,j
 is the initial direction of the cell (i,j)
. Please note that an,m=
 C.

Output
For each case, output in a new line the minimum number of cells that you have to change to make the conveyor belt functional.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int n,m;
        cin>>n>>m;
        vector<string>mat(n);
        for(auto &i:mat)
        cin>>i;
        int cnt=0;
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(i==n-1 && j==m-1)
                break;
                if(mat[i][j]=='R' && j+1==m)
                {mat[i][j]=='D';cnt++;}
                if(mat[i][j]=='D' && i+1==n)
                {mat[i][j]=='R';cnt++;}
            }
        }
        cout<<cnt<<endl;
    }
}
```

### 28 String Task

Petya started to attend programming lessons. On the first lesson his task was to write a simple program. The program was supposed to do the following: in the given string, consisting if uppercase and lowercase Latin letters, it:

deletes all the vowels,
inserts a character "." before each consonant,
replaces all uppercase consonants with corresponding lowercase ones.
Vowels are letters "A", "O", "Y", "E", "U", "I", and the rest are consonants. The program's input is exactly one string, it should return the output as a single string, resulting after the program's processing the initial string.

Help Petya cope with this easy task.

Input
The first line represents input string of Petya's program. This string only consists of uppercase and lowercase Latin letters and its length is from 1 to 100, inclusive.

Output
Print the resulting string. It is guaranteed that this string is not empty.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string s;
    cin>>s;
    string res;
    set<char>seto={'a','A','e','E','i','I','o','O','u','U','y','Y'};
    for(int i=0;i<s.size();i++){
        if(seto.find(s[i])!=seto.end())
        continue;
        else if(s[i]>='A' && s[i]<='Z')
        {
            res+='.';
            res+=(char)(s[i]+32);
        }
        else if(s[i]>='a' && s[i]<='z'){
            res+='.';
            res+=s[i];
        }else{
            res+=s[i];
        }
    }
    cout<<res<<endl;
}
```

### 29 Assigning to Classes

Reminder: the median of the array [a1,a2,…,a2k+1]
 of odd number of elements is defined as follows: let [b1,b2,…,b2k+1]
 be the elements of the array in the sorted order. Then median of this array is equal to bk+1
.

There are 2n
 students, the i
-th student has skill level ai
. It's not guaranteed that all skill levels are distinct.

Let's define skill level of a class as the median of skill levels of students of the class.

As a principal of the school, you would like to assign each student to one of the 2
 classes such that each class has odd number of students (not divisible by 2
). The number of students in the classes may be equal or different, by your choice. Every student has to be assigned to exactly one class. Among such partitions, you want to choose one in which the absolute difference between skill levels of the classes is minimized.

What is the minimum possible absolute difference you can achieve?

Input
Each test contains multiple test cases. The first line contains the number of test cases t
 (1≤t≤104
). The description of the test cases follows.

The first line of each test case contains a single integer n
 (1≤n≤105
) — the number of students halved.

The second line of each test case contains 2n
 integers a1,a2,…,a2n
 (1≤ai≤109
) — skill levels of students.

It is guaranteed that the sum of n
 over all test cases does not exceed 105
.

Output
For each test case, output a single integer, the minimum possible absolute difference between skill levels of two classes of odd sizes.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        vector<int>a(2*n);
        for(auto &i:a)
        cin>>i;
        sort(a.begin(),a.end());
        cout<<a[n]-a[n-1]<<endl;
    }
}
```

### 30 Numbers on Whiteboard

Numbers 1,2,3,…n
 (each integer from 1
 to n
 once) are written on a board. In one operation you can erase any two numbers a
 and b
 from the board and write one integer a+b2
 rounded up instead.

You should perform the given operation n−1
 times and make the resulting number that will be left on the board as small as possible.

For example, if n=4
, the following course of action is optimal:

choose a=4
 and b=2
, so the new number is 3
, and the whiteboard contains [1,3,3]
;
choose a=3
 and b=3
, so the new number is 3
, and the whiteboard contains [1,3]
;
choose a=1
 and b=3
, so the new number is 2
, and the whiteboard contains [2]
.
It's easy to see that after n−1
 operations, there will be left only one number. Your goal is to minimize it.

Input
The first line contains one integer t
 (1≤t≤1000
) — the number of test cases.

The only line of each test case contains one integer n
 (2≤n≤2⋅105
) — the number of integers written on the board initially.

It's guaranteed that the total sum of n
 over test cases doesn't exceed 2⋅105
.

Output
For each test case, in the first line, print the minimum possible number left on the board after n−1
 operations. Each of the next n−1
 lines should contain two integers — numbers a
 and b
 chosen and erased in each operation.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        vector<pair<int,int>>vp;
        int curr=n;
        for(int i=n;i>1;i--){
            vp.push_back({curr,i-1});
            curr=i;
        }
        cout<<curr<<endl;
        for(auto pi:vp)
        cout<<pi.first<<" "<<pi.second<<endl;
    }
}
```

### 31 Petr and Book

One Sunday Petr went to a bookshop and bought a new book on sports programming. The book had exactly n pages.

Petr decided to start reading it starting from the next day, that is, from Monday. Petr's got a very tight schedule and for each day of the week he knows how many pages he will be able to read on that day. Some days are so busy that Petr will have no time to read whatsoever. However, we know that he will be able to read at least one page a week.

Assuming that Petr will not skip days and will read as much as he can every day, determine on which day of the week he will read the last page of the book.

Input
The first input line contains the single integer n (1 ≤ n ≤ 1000) — the number of pages in the book.

The second line contains seven non-negative space-separated integers that do not exceed 1000 — those integers represent how many pages Petr can read on Monday, Tuesday, Wednesday, Thursday, Friday, Saturday and Sunday correspondingly. It is guaranteed that at least one of those numbers is larger than zero.

Output
Print a single number — the number of the day of the week, when Petr will finish reading the book. The days of the week are numbered starting with one in the natural order: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    vector<int>days(7);
    for(auto &i:days)
    cin>>i;
    int cnt=n;
    int i=0;
    while(cnt>0){
        i%=7;
        cnt-=days[i];
        cnt=max(cnt,0);
        i++;
    }
    cout<<i<<endl;
}
```

### 32 k-String

A string is called a k-string if it can be represented as k concatenated copies of some string. For example, the string "aabaabaabaab" is at the same time a 1-string, a 2-string and a 4-string, but it is not a 3-string, a 5-string, or a 6-string and so on. Obviously any string is a 1-string.

You are given a string s, consisting of lowercase English letters and a positive integer k. Your task is to reorder the letters in the string s in such a way that the resulting string is a k-string.

Input
The first input line contains integer k (1 ≤ k ≤ 1000). The second line contains s, all characters in s are lowercase English letters. The string length s satisfies the inequality 1 ≤ |s| ≤ 1000, where |s| is the length of string s.

Output
Rearrange the letters in string s in such a way that the result is a k-string. Print the result on a single output line. If there are multiple solutions, print any of them.

If the solution doesn't exist, print "-1" (without quotes).

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int k;
    cin>>k;
    string s;
    cin>>s;
    map<char,int>mp;
    for(auto c:s)
    mp[c]++;
    bool chk=true;
    for(auto item:mp){
        if(item.second%k!=0)
        {
            chk=false;
            break;
        }
    }
    if(!chk)
    cout<<"-1";
    else{
        string res;
        for(auto item:mp){
            for(int i=0;i<item.second/k;i++)
            res+=item.first;
        }
        int repeat=s.size()/res.size()-1;
        string temp=res;
        while(repeat--)
        res+=temp;
        cout<<res<<endl;
    }
}
```

### 33 Game 23

Polycarp plays "Game 23". Initially he has a number n
 and his goal is to transform it to m
. In one move, he can multiply n
 by 2
 or multiply n
 by 3
. He can perform any number of moves.

Print the number of moves needed to transform n
 to m
. Print -1 if it is impossible to do so.

It is easy to prove that any way to transform n
 to m
 contains the same number of moves (i.e. number of moves doesn't depend on the way of transformation).

Input
The only line of the input contains two integers n
 and m
 (1≤n≤m≤5⋅108
).

Output
Print the number of moves to transform n
 to m
, or -1 if there is no solution.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n,m;
    cin>>n>>m;
    if(m%n==0)
    {
        if(m/n==1)
        cout<<0<<endl;
        else{
            int val=m/n,cnt=0;
            while(val%3==0)
            {val/=3;cnt++;}
            while(val%2==0)
            {val/=2;cnt++;}
            if(val==1)
            cout<<cnt<<endl;
            else
            cout<<-1<<endl;
        }
    }
    else
        cout<<-1<<endl;
}
```

### 34 Present from Lena

Vasya's birthday is approaching and Lena decided to sew a patterned handkerchief to him as a present. Lena chose digits from 0 to n as the pattern. The digits will form a rhombus. The largest digit n should be located in the centre. The digits should decrease as they approach the edges. For example, for n = 5 the handkerchief pattern should look like that:

```txt
          0
        0 1 0
      0 1 2 1 0
    0 1 2 3 2 1 0
  0 1 2 3 4 3 2 1 0
0 1 2 3 4 5 4 3 2 1 0
  0 1 2 3 4 3 2 1 0
    0 1 2 3 2 1 0
      0 1 2 1 0
        0 1 0
          0
```

Your task is to determine the way the handkerchief will look like by the given n.

Input
The first line contains the single integer n (2 ≤ n ≤ 9).

Output
Print a picture for the given n. You should strictly observe the number of spaces before the first digit on each line. Every two adjacent digits in the same line should be separated by exactly one space. There should be no spaces after the last digit at the end of each line.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    for(int i=0;i<n;i++){
        for(int k=0;k<2*(n-i);k++)
        cout<<" ";
        int j;
        if(i==0){
            cout<<0<<endl;
        }
        else{
            for(j=0;j<=i;j++)
            cout<<j<<" ";
            j-=2;
            for(;j>0;j--)
            cout<<j<<" ";
            cout<<j;
            cout<<endl;
        }
    }
    for(int i=n;i>=0;i--){
        for(int k=0;k<2*(n-i);k++)
        cout<<" ";
        int j;
        if(i==0){
            cout<<0<<endl;
        }
        else{
            for(j=0;j<=i;j++)
            cout<<j<<" ";
            j-=2;
            for(;j>0;j--)
            cout<<j<<" ";
            cout<<j;
            cout<<endl;
        }
    }
}
```

### 35 Donut Shops

There are two rival donut shops.

The first shop sells donuts at retail: each donut costs a
 dollars.

The second shop sells donuts only in bulk: box of b
 donuts costs c
 dollars. So if you want to buy x
 donuts from this shop, then you have to buy the smallest number of boxes such that the total number of donuts in them is greater or equal to x
.

You want to determine two positive integer values:

how many donuts can you buy so that they are strictly cheaper in the first shop than in the second shop?
how many donuts can you buy so that they are strictly cheaper in the second shop than in the first shop?
If any of these values doesn't exist then that value should be equal to −1
. If there are multiple possible answers, then print any of them.

The printed values should be less or equal to 109
. It can be shown that under the given constraints such values always exist if any values exist at all.

Input
The first line contains a single integer t
 (1≤t≤1000
) — the number of testcases.

Each of the next t
 lines contains three integers a
, b
 and c
 (1≤a≤109
, 2≤b≤109
, 1≤c≤109
).

Output
For each testcase print two positive integers. For both shops print such x
 that buying x
 donuts in this shop is strictly cheaper than buying x
 donuts in the other shop. x
 should be greater than 0
 and less or equal to 109
.

If there is no such x
, then print −1
. If there are multiple answers, then print any of them.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int t;
    cin>>t;
    while(t--){
        int a,b,c;
        cin>>a>>b>>c;
        if(a>=c)
        cout<<-1<<" ";
        else
        cout<<1<<" ";
        if(c/b>=a)
        cout<<-1<<endl;
        else
        cout<<b<<endl;
    }
}
```

### 36 Buttons

Manao is trying to open a rather challenging lock. The lock has n buttons on it and to open it, you should press the buttons in a certain order to open the lock. When you push some button, it either stays pressed into the lock (that means that you've guessed correctly and pushed the button that goes next in the sequence), or all pressed buttons return to the initial position. When all buttons are pressed into the lock at once, the lock opens.

Consider an example with three buttons. Let's say that the opening sequence is: {2, 3, 1}. If you first press buttons 1 or 3, the buttons unpress immediately. If you first press button 2, it stays pressed. If you press 1 after 2, all buttons unpress. If you press 3 after 2, buttons 3 and 2 stay pressed. As soon as you've got two pressed buttons, you only need to press button 1 to open the lock.

Manao doesn't know the opening sequence. But he is really smart and he is going to act in the optimal way. Calculate the number of times he's got to push a button in order to open the lock in the worst-case scenario.

Input
A single line contains integer n (1 ≤ n ≤ 2000) — the number of buttons the lock has.

Output
In a single line print the number of times Manao has to push a button in the worst-case scenario.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    int cnt=n;
    int res=cnt;
    cnt--;
    for(int step=2;step<=n;step++){
        if(step!=n)
        res+=(step-1)*(cnt-1)+cnt;
        else
        res++;
        cnt--;
    }
    cout<<res;
}
```

### 37 Dreamoon and Stairs

Dreamoon wants to climb up a stair of n steps. He can climb 1 or 2 steps at each move. Dreamoon wants the number of moves to be a multiple of an integer m.

What is the minimal number of moves making him climb to the top of the stairs that satisfies his condition?

Input
The single line contains two space separated integers n, m (0 < n ≤ 10000, 1 < m ≤ 10).

Output
Print a single integer — the minimal number of moves being a multiple of m. If there is no way he can climb satisfying condition print  - 1 instead.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n,m;
    cin>>n>>m;
    if(n<m)
    cout<<-1<<endl;
    else{
        int mino,maxo=n;
        if(n%2==0)
        mino=n/2;
        else
        mino=n/2+1;
        int res;
        for(int i=mino;i<=maxo;i++)
        {
            if(i%m==0){
                res=i;
                break;
            }
        }
        cout<<res<<endl;
    }
}
```

### 38 New Year Transportation

New Year is coming in Line World! In this world, there are n cells numbered by integers from 1 to n, as a 1 × n board. People live in cells. However, it was hard to move between distinct cells, because of the difficulty of escaping the cell. People wanted to meet people who live in other cells.

So, user tncks0121 has made a transportation system to move between these cells, to celebrate the New Year. First, he thought of n - 1 positive integers a1, a2, ..., an - 1. For every integer i where 1 ≤ i ≤ n - 1 the condition 1 ≤ ai ≤ n - i holds. Next, he made n - 1 portals, numbered by integers from 1 to n - 1. The i-th (1 ≤ i ≤ n - 1) portal connects cell i and cell (i + ai), and one can travel from cell i to cell (i + ai) using the i-th portal. Unfortunately, one cannot use the portal backwards, which means one cannot move from cell (i + ai) to cell i using the i-th portal. It is easy to see that because of condition 1 ≤ ai ≤ n - i one can't leave the Line World using portals.

Currently, I am standing at cell 1, and I want to go to cell t. However, I don't know whether it is possible to go there. Please determine whether I can go to cell t by only using the construted transportation system.

Input
The first line contains two space-separated integers n (3 ≤ n ≤ 3 × 104) and t (2 ≤ t ≤ n) — the number of cells, and the index of the cell which I want to go to.

The second line contains n - 1 space-separated integers a1, a2, ..., an - 1 (1 ≤ ai ≤ n - i). It is guaranteed, that using the given transportation system, one cannot leave the Line World.

Output
If I can go to cell t using the transportation system, print "YES". Otherwise, print "NO".

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    int n,t;
    cin>>n>>t;
    vector<int>a(n);
    for(int i=1;i<n;i++)
    cin>>a[i];
    int curr=1;
    while(curr<t)
        curr+=a[curr];
    if(curr==t)
    cout<<"YES\n";
    else
    cout<<"NO\n";
}
```

### 39 cAPS lOCK

wHAT DO WE NEED cAPS LOCK FOR?

Caps lock is a computer keyboard key. Pressing it sets an input mode in which typed letters are capital by default. If it is pressed by accident, it leads to accidents like the one we had in the first passage.

Let's consider that a word has been typed with the Caps lock key accidentally switched on, if:

either it only contains uppercase letters;
or all letters except for the first one are uppercase.
In this case we should automatically change the case of all letters. For example, the case of the letters that form words "hELLO", "HTTP", "z" should be changed.

Write a program that applies the rule mentioned above. If the rule cannot be applied, the program should leave the word unchanged.

Input
The first line of the input data contains a word consisting of uppercase and lowercase Latin letters. The word's length is from 1 to 100 characters, inclusive.

Output
Print the result of the given word's processing.

```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    string s;
    cin>>s;
    bool type1=false,type2=false;
    for(int i=0;i<s.size();i++){
        if(i==0 && (s[i]>='A' && s[i]<='Z'))
            type1=true;
        else if(i==0 && (s[i]>='a' && s[i]<='z'))
            type2=true;
        else if(i!=0 && type1 && s[i]>='a' && s[i]<='z')
        {
            cout<<s<<endl;
            return 0;
        }
        else if(i!=0 && type2 && s[i]>='a' && s[i]<='z'){
            cout<<s<<endl;
            return 0;
        }
    }
    if(type1){
        for(int i=0;i<s.size();i++)
        s[i]=(char)(s[i]+32);
        cout<<s<<endl;
    }else if(type2){
        s[0]=(char)(s[0]-32);
        for(int i=1;i<s.size();i++)
        s[i]=(char)(s[i]+32);
        cout<<s<<endl;
    }
}
```

### 40 Chocolates

You went to the store, selling n
 types of chocolates. There are ai
 chocolates of type i
 in stock.

You have unlimited amount of cash (so you are not restricted by any prices) and want to buy as many chocolates as possible. However if you buy xi
 chocolates of type i
 (clearly, 0≤xi≤ai
), then for all 1≤j<i
 at least one of the following must hold:

xj=0
 (you bought zero chocolates of type j
)
xj<xi
 (you bought less chocolates of type j
 than of type i
)
For example, the array x=[0,0,1,2,10]
 satisfies the requirement above (assuming that all ai≥xi
), while arrays x=[0,1,0]
, x=[5,5]
 and x=[3,2]
 don't.

Calculate the maximum number of chocolates you can buy.

Input
The first line contains an integer n
 (1≤n≤2⋅105
), denoting the number of types of chocolate.

The next line contains n
 integers ai
 (1≤ai≤109
), denoting the number of chocolates of each type.

Output
Print the maximum number of chocolates you can buy.

```cpp
#include<bits/stdc++.h>
#define int long long
using namespace std;
int32_t main(){
   int n;
   cin>>n;
   vector<int>a(n);
   for(auto &ele:a)
   cin>>ele;
   int res=0,min_till_now=INT_MAX;
   for(int i=n-1;i>=0;i--){
        if(min_till_now>a[i])
        min_till_now=a[i];
        else
        min_till_now--;
        res+=min_till_now;
        if(min_till_now==1)
        break;
   }
   cout<<res;
}
```

### 41 City Day

For years, the Day of city N was held in the most rainy day of summer. New mayor decided to break this tradition and select a not-so-rainy day for the celebration. The mayor knows the weather forecast for the n
 days of summer. On the i
-th day, ai
 millimeters of rain will fall. All values ai
 are distinct.

The mayor knows that citizens will watch the weather x
 days before the celebration and y
 days after. Because of that, he says that a day d
 is not-so-rainy if ad
 is smaller than rain amounts at each of x
 days before day d
 and and each of y
 days after day d
. In other words, ad<aj
 should hold for all d−x≤j<d
 and d<j≤d+y
. Citizens only watch the weather during summer, so we only consider such j
 that 1≤j≤n
.

Help mayor find the earliest not-so-rainy day of summer.

Input
The first line contains three integers n
, x
 and y
 (1≤n≤100000
, 0≤x,y≤7
) — the number of days in summer, the number of days citizens watch the weather before the celebration and the number of days they do that after.

The second line contains n
 distinct integers a1
, a2
, ..., an
 (1≤ai≤109
), where ai
 denotes the rain amount on the i
-th day.

Output
Print a single integer — the index of the earliest not-so-rainy day of summer. We can show that the answer always exists.

```cpp
#include<bits/stdc++.h>
#define int long long 
using namespace std;
int32_t main(){
    int n,x,y;
    cin>>n>>x>>y;
    vector<int>a(n);
    for(auto &ele:a)
    cin>>ele;
    for(int i=0;i<n;i++){
        int idx1=i-1;
        int mino=INT_MAX;
        while(idx1>=0 && idx1>=i-x)
            mino=min(mino,a[idx1--]);
        mino=min(mino,a[i]);
        idx1=i+1; 
        while(idx1<n && idx1<=i+y)
            mino=min(mino,a[idx1++]);
        if(mino==a[i])
        {
            cout<<i+1<<endl;
            return 0;
        }    
    }
}
```

### 42 Diverse Substring

You are given a string s
, consisting of n
 lowercase Latin letters.

A substring of string s
 is a continuous segment of letters from s
. For example, "defor" is a substring of "codeforces" and "fors" is not.

The length of the substring is the number of letters in it.

Let's call some string of length n
 diverse if and only if there is no letter to appear strictly more than n2
 times. For example, strings "abc" and "iltlml" are diverse and strings "aab" and "zz" are not.

Your task is to find any diverse substring of string s
 or report that there is none. Note that it is not required to maximize or minimize the length of the resulting substring.

Input
The first line contains a single integer n
 (1≤n≤1000
) — the length of string s
.

The second line is the string s
, consisting of exactly n
 lowercase Latin letters.

Output
Print "NO" if there is no diverse substring in the string s
.

Otherwise the first line should contain "YES". The second line should contain any diverse substring of string s
.

```cpp
#include<bits/stdc++.h>
#define int long long 
using namespace std;
int32_t main(){
    int n;
    cin>>n;
    string s;
    cin>>s;
    if(n<=1)
    {
        cout<<"NO\n";
        return 0;
    }
    map<char,int>mp;
    for(int i=0;i<2;i++)
        mp[s[i]]++;
    if(mp.size()==2){
        cout<<"YES\n"<<s.substr(0,2);
        return 0;
    }
    for(int i=2;i<n;i++){
        mp[s[i-2]]--;
        if(mp[s[i-2]]==0)
        mp.erase(s[i-2]);
        mp[s[i]]++;
        if(mp.size()==2){
            cout<<"YES\n"<<s.substr(i-1,2);
            return 0;
        }
    }
    cout<<"NO\n";
}
```

### 43 Lucky Sum of Digits

Petya loves lucky numbers. We all know that lucky numbers are the positive integers whose decimal representations contain only the lucky digits 4 and 7. For example, numbers 47, 744, 4 are lucky and 5, 17, 467 are not.

Petya wonders eagerly what minimum lucky number has the sum of digits equal to n. Help him cope with the task.

Input
The single line contains an integer n (1 ≤ n ≤ 106) — the sum of digits of the required lucky number.

Output
Print on the single line the result — the minimum lucky number, whose sum of digits equals n. If such number does not exist, print -1.

```cpp
#include<bits/stdc++.h>
#define int long long 
using namespace std;
int32_t main(){
    int n;
    cin>>n;
    int max4=n/4,max7=n/7,res4,res7,cnt_digit=INT_MAX;
    bool chk=false;
    for(int i=0;i<=max4;i++){
        for(int j=0;j<=max7;j++){
            if((i*4+j*7)==n){
                res4=i;
                res7=j;
                chk=true;
                break;
            }
        }
        if(chk)
        break;
    }
    if(chk){
        for(int i=0;i<res4;i++)
        cout<<4;
        for(int i=0;i<res7;i++)
        cout<<7;
    }else
    cout<<-1;
}
```

### 44 Rooms and Staircases

Nikolay lives in a two-storied house. There are n
 rooms on each floor, arranged in a row and numbered from one from left to right. So each room can be represented by the number of the floor and the number of the room on this floor (room number is an integer between 1
 and n
).

If Nikolay is currently in some room, he can move to any of the neighbouring rooms (if they exist). Rooms with numbers i
 and i+1
 on each floor are neighbouring, for all 1≤i≤n−1
. There may also be staircases that connect two rooms from different floors having the same numbers. If there is a staircase connecting the room x
 on the first floor and the room x
 on the second floor, then Nikolay can use it to move from one room to another.

The picture illustrates a house with n=4
. There is a staircase between the room 2
 on the first floor and the room 2
 on the second floor, and another staircase between the room 4
 on the first floor and the room 4
 on the second floor. The arrows denote possible directions in which Nikolay can move. The picture corresponds to the string "0101" in the input.
Nikolay wants to move through some rooms in his house. To do this, he firstly chooses any room where he starts. Then Nikolay moves between rooms according to the aforementioned rules. Nikolay never visits the same room twice (he won't enter a room where he has already been).

Calculate the maximum number of rooms Nikolay can visit during his tour, if:

he can start in any room on any floor of his choice,
and he won't visit the same room twice.
Input
The first line of the input contains one integer t
 (1≤t≤100
) — the number of test cases in the input. Then test cases follow. Each test case consists of two lines.

The first line contains one integer n
 (1≤n≤1000)
 — the number of rooms on each floor.

The second line contains one string consisting of n
 characters, each character is either a '0' or a '1'. If the i
-th character is a '1', then there is a staircase between the room i
 on the first floor and the room i
 on the second floor. If the i
-th character is a '0', then there is no staircase between the room i
 on the first floor and the room i
 on the second floor.

In hacks it is allowed to use only one test case in the input, so t=1
 should be satisfied.

Output
For each test case print one integer — the maximum number of rooms Nikolay can visit during his tour, if he can start in any room on any floor, and he won't visit the same room twice.

```cpp
#include<bits/stdc++.h>
#define int long long 
using namespace std;
int32_t main(){
    int t;
    cin>>t;
    while(t--){
        int n;
        cin>>n;
        string s;
        cin>>s;
        int idx1=INT_MAX;
        for(int i=0;i<n;i++)
        {
            if(s[i]=='1' && i<idx1)
            idx1=i;
            if(s[i]=='1' && (n-i-1)<idx1)
            idx1=n-i-1;
        }
        if(idx1==INT_MAX)
        cout<<n<<endl;
        else
        cout<<2*(n-idx1)<<endl;
    }
}
```
