#include<iostream>
using namespace std;

//Binary search for array with unknown length
int BinarySearch_Unknown(int arr[],int key){
    //Initializing i as 0 and j as 1.
    int i=0,j=1;
    //We will increase j until arr[j] exceeds key to be searched.
    while(arr[j]<key){
        i=j;
        j=2*j;
    }
    //Now calling Simple Binary Search on range i to j.
    return BinarySearch(arr,i,j,key);
}


int BinarySearch(int arr[],int i,int j,int key){
    int m=(i+j)/2; //m=middle element
    while(i<=j){   //i=starting index & j=ending index
    if(arr[m]==key){return m;}  // if key to be searched is present it returns index of that key
    else{
        if(arr[m]<key){i=m+1;}
        else{j=m-1;}
    }
    m=(i+j)/2;
    }
    return -1;  // when element is not present we will return -1
}
