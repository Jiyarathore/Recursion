![image](https://github.com/Jiyarathore/Recursion/assets/96529109/f62fcb67-2cfa-4fe3-ad5d-116db50c02ed)
![image](https://github.com/Jiyarathore/Recursion/assets/96529109/5bb9866a-32ec-4cab-a0cc-5532ee41f40c)
![image](https://github.com/Jiyarathore/Recursion/assets/96529109/f1f507b4-2383-44e1-8e35-17977c8e4ca4)


#include <bits/stdc++.h>
using namespace std;
void removeM(stack<int>&stk,int k){
    if(stk.size()==k){
        stk.pop();
        return ;
    }
    int temp = stk.top();
    stk.pop();
    removeM(stk,k);
    stk.push(temp);
}
int main()
{
    stack<int>stk;
    int arr[]={55,44,33,22,11};
    for(int i=0;i<sizeof(arr)/sizeof(arr[0]);i++){
        stk.push(arr[i]);
    }
    int k = stk.size()/2 +1 ;
    removeM(stk,k);
    cout<<"\nElements of the stack after removal of middle element is: ";
    while(!stk.empty()){
        cout<<stk.top()<<"  ";
        stk.pop();
    }
}
