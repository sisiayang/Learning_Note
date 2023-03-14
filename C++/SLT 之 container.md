### Set
特性：  
* 每個元素唯一存在，且不可更改 (const)
* 按照特定順序存放，非插入順序 (用red-black tree實作)

常用operation：
* s.insert(x)
* s.erase(x)
* set<int>::iterator itr = s.find(x)  

若是試圖insert重複的元素、erase不存在的元素，皆不會造成error(可能底層有寫好防呆?)  
迭代器若是等於s.end()即表示沒有找到該元素

---
### Map
特性：
* 由key, value組成，其中key值唯一，若是要insert相同key值的資料，原本的資料會被覆蓋
* 底層實作為red-black tree (按照key值) -> operation為O(nlogn)
* 存取元素使用m[key]

常用operation：
* m.insert(make_pair(k, v))
* m.erase(k)
* map<string, int>::iterator itr = m.find(k)

