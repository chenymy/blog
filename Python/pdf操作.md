# pdf操作

## pdf去文字水印

- ### 方法一

  pip install pymupdf

  ```python
  import fitz  # import the pymupdf library
  
  pdf = fitz.open("测试.pdf")
  # 水印内容，比如Spire.Doc进行word转pdf产生的水印
  watermark = 'Evaluation Warning: The document was created with Spire.Doc for Python.'
  # watermark = 'Evaluation Warning : The document was created with Spire.Presentation for Python'
  for page in pdf:
      # 1. 找到需要删除或替换的文本块, 然后添加修订注释(redaction annotation)
      # 2. 添加注释后, 步骤1的文本块会被删除
      # 3. 还可以在原位置添加新的文本块
      blocks = page.get_text("dict")["blocks"]
      for j, block in enumerate(blocks):
          if watermark in str(block):
              for line in block['lines']:
                  for span in line['spans']:
                      text = span.get('text', '')
                      if text == watermark:
                          page.add_redact_annot(span['bbox'])
                          # page.add_redact_annot(span['bbox'], '替换新的文本', fontname='china-s', fontsize=span['size'])
                          page.apply_redactions()
  pdf.save('测试.pdf')
  pdf.close()
  
  ```
  
  