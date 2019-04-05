# python-copy

```python
from datetime import datetime
from os import mkdir, path, remove, walk
from shutil import copy2, move
from time import strftime

root_src_dir = path.join('', r'C:\Users\agupta78\Desktop\folder1')
root_dst_dir = path.join('', r'C:\Users\agupta78\Desktop\folder2')

operation = 'copy'  # 'copy' or 'move'

for src_dir, dirs, files in walk(root_src_dir):
    dst_dir = src_dir.replace(root_src_dir, root_dst_dir)
    if not path.exists(dst_dir):
        mkdir(dst_dir)
    for file_ in files:
        src_file = path.join(src_dir, file_)
        dst_file = path.join(dst_dir, file_)
        if path.exists(dst_file):
            remove(dst_file)
        if operation is 'copy':
            copy2(src_file, dst_dir)
        elif operation is 'move':
            move(src_file, dst_dir)

current_date = str(datetime.now().strftime('%d_%m_%Y'))
print(current_date)

files_list = listdir(root_dst_dir)
print(files_list)
chdir(root_dst_dir)
for file_name in files_list:
    rename(file_name, file_name + current_date)

# for dst_file in walk(dst_dir):
#     file_time = str(datetime.now().strftime('%d_%m_%Y'))
#     # tupe_to_string = ''.join(dst_file)
#     full_path = path.join(
#         path.abspath(fsdecode(dst_file)), sep, file_time)

```


```python
from datetime import datetime
import os

file_path = <PASS YOUR FILE HERE>

csv_file = 'myfile_' + str(datetime.now().strftime('%Y_%m_%d_%H_%M_%S')) + '.csv'

csv_file_full = os.path.join(file_path, os.sep, csv_file)
```

```python
import time
timestr = time.strftime("_%d_%m_%Y")
print(timestr)
```
