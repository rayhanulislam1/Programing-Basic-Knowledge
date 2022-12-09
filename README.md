<h1 align="center">Standard Template Library (STL)</h1>

## Array
```c++
int arr[10] = {1, 12, 3, 24, 35, 16};  
   sort(arr, arr+10, [](int i, int j){  
       return i > j;  
   });   
   F0R(i, 10){  
       cout << arr[i] << " ";  
   }
 ```
