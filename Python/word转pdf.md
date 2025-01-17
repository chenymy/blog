## word转pdf

- ### 以来office应用的略

- ### 方法一

  pip install Spire.Doc

  有水印

  ```python
  import time
  from spire.doc import *
  from spire.doc.common import *
  
  aa = time.time()
  docx_file = r"测试.docx"
  pdf_file = r'测试.pdf'
  document = Document()
  document.LoadFromFile(docx_file)
  document.SaveToFile(pdf_file, FileFormat.PDF)
  document.Close()
  print(time.time() - aa)	# 0.6396734714508057
  ```

- ### 方法二

  pip install aspose-words

  有水印

  ```python
  import time
  import aspose.words as aw
  
  aa = time.time()
  docx_file = r"测试.docx"
  pdf_file = r'测试.pdf'
  doc = aw.Document(docx_file)
  doc.save(pdf_file)
  print(time.time() - aa)	# 1.8513450622558594
  ```

  ### 其他

  去水印参考其他文档