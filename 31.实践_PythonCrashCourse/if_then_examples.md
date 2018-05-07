

### 1. Create multiple files or directories with for loop

```python
在文本里写好了chapter,想要新建多个同名的文件.
chapters = [ 'Chapter 1: Getting Started',
             'Chapter 2: Variables and Simple Data Types',
             'Chapter 3: Introducing Lists',
             'Chapter 4: Working with Lists',
             'Chapter 5: if Statements',
             'Chapter 6: Dictionaries',
             'Chapter 7: User Input and while Loops',
             'Chapter 8: Functions',
             'Chapter 9: Classes',
             'Chapter 10: Files and Exceptions',
             'Chapter 11: Testing Your Code']
#solution 1
for chapter in chapters:
    with open(chapter+".md", 'w'):
        pass
#solution 2
import subprocess
for chapter in chapters:
    subprocess.run(chapter+'.md', shell=True)
```

| Codes                                                        | Results                                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Screen Shot 2018-05-06 at 9.40.03 PM](https://ws1.sinaimg.cn/large/006tKfTcly1fr1ysfy6nhj30su0j4n0i.jpg) | ![Screen Shot 2018-05-06 at 9.43.23 PM](https://ws4.sinaimg.cn/large/006tKfTcly1fr1ysgr4bvj30n80cijtz.jpg) |
| ![Screen Shot 2018-05-06 at 9.41.52 PM](https://ws2.sinaimg.cn/large/006tKfTcly1fr1ysg6k2cj30s40720td.jpg) |                                                              |

