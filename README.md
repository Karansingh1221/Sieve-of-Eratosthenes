# Sieve-of-Eratosthenes
# The sieve of Eratosthenes is one of the most efficient ways to find all primes smaller than or equal to n when n is smaller than 10 million or so
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
void sieceOfEratosthenes(int n){
	bool prime[n+1];
	memset(prime,true,sizeof(prime));//memset function set the same value upto the given memory size
	for(int i=2;i*i<=n;i++){
		if(prime[i]){
			for(int p=i*i;p<=n;p+=i){
				prime[p]=false;
			}
		}
	}
	for(int i=2;i<=n;i++){
		if(prime[i]){
			cout<<i<<" ";
		}
	}
}
int main(){
	int n;
	cout<<"Enter the number upto which you want to print the numbers: ";
	cin>>n;
	sieceOfEratosthenes(n);
}
