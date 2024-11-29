## json中dumps、dump、loads、load详解

- dumps：将字典转换成json字符串

  ```python
  import json
  a = {
          "a": "1111",
          "c": "3333",
          "b": "2222",
          "d": "4444"
      }
  
  print(json.dumps(a))
  
  输出：{"d": "4444", "b": "2222", "c": "3333", "a": "1111"}
  ```

- dump:将字典转换成json字符串并将其写入json文件中

  ```python
  import json
  a = {
          "a": "1111",
          "c": "3333",
          "b": "2222",
          "d": "4444"
      }
  
  json.dump(a,open('dump.json','w'))
  ```

- loads:将json字符串转换成字典

  ```python
  import json
  a = '''{
          "a": "1111",
          "c": "3333",
          "b": "2222",
          "d": "4444"
      }'''
  
  print(json.loads(a))
  
  输出：{'c': '3333', 'a': '1111', 'b': '2222', 'd': '4444'}
  ```

- load:将json文件中的数据读出生成json字符串

  ```python
  import json
  
  print(json.load(open('dump.json','r')))
  ```

  