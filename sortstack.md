![image](https://github.com/Jiyarathore/Recursion/assets/96529109/1e6d32f7-db49-4d5e-9da1-613e00ec3ce6)
![image](https://github.com/Jiyarathore/Recursion/assets/96529109/90433e19-a8af-43ae-8432-90dd87cbaae3)
![image](https://github.com/Jiyarathore/Recursion/assets/96529109/44276dee-ad5e-4930-8829-f416bc1a22af)
![image](https://github.com/Jiyarathore/Recursion/assets/96529109/a1d3a3a6-df11-4ff9-81eb-78a1092a8a40)
#include <bits/stdc++.h>
using namespace std;
void insert(stack<int> &st, int k)
{
    int n = st.size();
    if (n == 0 || st.top() <= k)
    {
        st.push(k);
        return;
    }
    int val = st.top();
    st.pop();
    insert(st, k);
    st.push(val);
}
void sort(stack<int> &st)
{
    int n = st.size();
    if (n == 0 || n == 1)
        return;
    int temp = st.top();
    st.pop();
    sort(st);
    insert(st, temp);
}
int main()
{
    stack<int> st;
    int n;
    cout << "enter the size of stack";
    cin >> n;
    for (int i = 0; i < n; i++)
    {
        int k;
        cin >> k;
        st.push(k);
    }
    sort(st);
    cout << "\nsorted stack in descending order:\n";

    while (!st.empty())
    {
        cout << st.top() << " ";
        st.pop();
    }
    return 0;
}

