![image](https://github.com/Jiyarathore/Recursion/assets/96529109/2052684b-435d-4a76-ac1b-00666efbd3d8)
![image](https://github.com/Jiyarathore/Recursion/assets/96529109/c991d510-8a4d-4103-bcc6-fc56a4361981)
#include <bits/stdc++.h>
using namespace std;

void Insert(vector<int> &v, int temp){
	if(v.size() == 0 || v[v.size()-1] <=temp){
		v.push_back(temp);
		return;
	}
	int val = v[v.size()-1];
	v.pop_back();
	Insert(v,temp);
	v.push_back(val);
	return;


}
void Sort(vector<int> &v){
	if(v.size()==1){
		return;
	}
	int temp = v[v.size()-1]; // last element.
	v.pop_back();
    Sort(v);
    Insert(v, temp);
}




int main(){
	vector<int>v={9,0,1,4,90,67,2,120};
	Sort(v);

	for(int i=0; i<v.size(); i++){
		cout<<v[i]<<" ";
	}
}

