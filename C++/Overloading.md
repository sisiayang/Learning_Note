### Overloading

* ostream
  ```C++
  // s: 輸出串流，回傳後會在cout顯示出的值
  // Person: 
  ostream &operator<<(ostream &s, Person p){
    s << p.get_first_name() << " " << p.get_last_name();
    ...
    return s;
  }
  ```
* istream
  ```C++
  istream &operator>>(istream &s, Person p){
    s >> p.get_first_name() >> p.get_last_name();
    ...
    return s;
  }
  ```
