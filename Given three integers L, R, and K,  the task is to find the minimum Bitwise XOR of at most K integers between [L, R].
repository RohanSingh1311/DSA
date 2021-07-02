/*Given three integers L, R, and K, 
the task is to find the minimum Bitwise XOR of at most K integers between [L, R].

Examples:

Input: L = 1, R = 10, K = 3
Output: 0
Explanation:
Choose elements 4, 5, and 1 in the range [1, 10]
and the Bitwise XOR of the chosen elements is 0, which is minimum. 

Input: L = 32, R = 33, K = 2
Output: 1
Explanation:
Choose elements 32, and 33 in the range [32, 33] 
and the Bitwise XOR of the chosen elements is 1, which is minimum.

// Approach: An observation that helps us in solving the problem is 
the Bitwise XOR of two numbers X and (X+1) is 1 if X is an even number.
Thus, the Bitwise XOR of four consecutive numbers would be 0 if the first one is even*/


#include <iostream>
#include <bits/stdc++.h>
using namespace std;

int func2(int L, int R, int K){
    if(R-L>=2)
         return 1;
    return min(L, L ^ R);
}
int func3(int L, int R, int K){
    if((R ^ L) > L && (R ^ L) < R)
         return 0;
    return func2(L, R, K);
}
int func4(int L, int R, int K){
    if(R-L>=4)
        return 0;
    int minval = L ^ (L + 1) ^ (L + 2) ^ (L + 3);
    return min(minval, func3(L, R, K));
}

int minimumXOR(int L, int R, int K){
    if(K>4)
        return 0;
    else if (K == 4)
        return func4(L, R, K);
    else if (K == 3)
        return func3(L, R, K);
    else if (K == 2)
        return func2(L, R, K);
    else
        return L;
}

int main() {
	int L=32,R=33,k=2;
	cout<<minimumXOR(L,R,k);
	return 0;
}



/*Follow the steps below to solve the problem:

1) If the value of K is greater than 4 then the answer is always 0. 
(This is because four numbers X, (X+1), (X+2), and (X+3) can always be 
found in a range of 5 where X is an even number.)

2)If the value of K is 2, call the function func2() that takes L, R, and K as input 
parameters and does the following:
--> If the value of (R-L) is greater than or equal to 2 i.e. there are at least 3 numbers 
    in the range, return 1.(This is because two numbers X and X+1 can always be found in 
    a range of 3 where X is an even number.)
--> Otherwise, return the minimum of L and (L^R).

3)If the value of K is 3, call the function func3() that takes L, R, and K as input
parameters and does the following:
--> If (R^L) lies between L and R, return 0. (This is because (R^L)^L^R=0) )
--> Otherwise, return func2(L, R, K)

4)If the value of K is 4, call the function func4() that takes L, R, and K as input
parameters and does the following:
--> If (R-L) is greater than or equal to 4, i.e. there are at least 5 numbers in the range,
    return 0. (This is because four numbers X,(X+1),(X+2), and (X+3) can always be found 
    in a range of 5 where X is an even number.)
--> Otherwise, return the minimum of Xor of the four numbers in the range [L, R] and 
    func3(L, R, K).
5)Otherwise, return L.
*/
