# Map là gì?
- Map thuộc kiểu Associative Containers (Cấu trúc liên kết).  
- Cho phép ta quản lý một cặp "vị trí/dữ liệu"(position/data).  

# Lớp Pair
- Để sinh ra cặp đối tượng "position/ data" ta dùng lớp "pair".  
Cú pháp khai báo:  
`pair<data_type, data_type> variable_name;`  

```
pair<int, char*> mypair;

pair<int, char*> pair1(0, "a");

//Copy
pair<int, char*> copypair(pair1);
```
# Lớp Map

Khai Báo:  
```
map<int, char*> mymap;  
mymap[0] = "a";  
mymap[1] = "b";  
```  

- Lớp "map" được định nghĩa các hàm thành viên hỗ trợ cho việc truy xuất, lấy kích thước.  
```
map<char,int> first;
 
first['a'] = 10;
first['b'] = 30;
first['c'] = 50;
first['d'] = 70;
 
// range constructor
map<char,int> second (first.begin(), first.end());
 
// copy constructor
map<char,int> third (second);
```

- Lớp "map" cho phép ta truy xuất trực tiếp đến "position" của từng phần tử.  

- Có hàm thành viên insert() cho phép ta chèn thêm một đối tượng:  
```
map<int, char*> mymap, copymymap;  
mymap[0] = "a";  
mymap[1] = "b";  
mymap[5] = "c";  

// chèn vào copymymap cặp đối tượng (10, "c")	
copymymap.insert(pair<int, char*>(10, "c"));  

// chèn (-1, "d") vào copymymap từ vị trí bắt đầu của copymymap  
copymymap.insert(copymymap.begin(), pair<int, char*>(-1, "d"));  

// chèn mymap vào copymymap  
copymymap.insert(mymap.begin(), mymap.end());  
```
> => copymymap = {(-1,"d"),(0,"a"),(1,"b"),(5,"c"),(10,"c")}  

- Hàm thành viên erase() cho phép ta xóa một đối tượng hay hàm clear() cho phép ta xóa tất cả đối tượng trong "map".  
```
map<int, char*> mymap, copymymap;  
mymap[0] = "a";  
mymap[1] = "b";  
mymap[5] = "c";  
mymap[7] = "d";  
mymap[9] = "e";  

// xóa cặp đối tượng với "position" là 5  
mymap.erase(5);	 

// xóa toàn bộ đối tượng  
mymap.clear();  
```

- Với hàm thành viên swap() cho ta hoán đổi nội dung của lớp "map"
```
map<char,int> map1, map2;  
 
map1['x'] = 100;  
map1['y'] = 200;  
 
map2['a'] = 11;  
map2 ['b'] = 22;  
map2 ['c'] = 33;  
 
map1.swap(map2);  
```

> => map1 = {("x",11),("b",22),("c",33)}  
 => map2 = {("x",100),("y",200)}  

- Hàm thành viên find() cho phép ta tìm kiếm theo "position".  
`mymap.find("position")`  

> Copy & Paste tại [đây](https://www.stdio.vn/articles/stl-map-trong-c-76)  