### py-github-pass-reader
**Simple python script to read generated "github-recovery-codes.txt" file.**
---
# How to use it:
1. run the code:
```bash
python3 py_github_pass_reader.py
```
  
1. *Enter the file path*

---

``` python
import random

def main():
    file_path = input("file path: ")

    if(len(file_path) > 8):
        generate_pass(file_path)
    else:
        print("Try again.")
        main()

def generate_pass(file_path):
    pass_list = []
    filtered_pass_list = []
    try:
        with open(file_path, "r") as files:
            for file in files:
                pass_list.append(file)

            for pass_item in pass_list:
                filtered_pass_list.append(pass_item.replace("\n", ""))

        print("\n" + "-"*4 + " Result " + "-"*4)
        print("Your Password: " + str(random.choice(filtered_pass_list)))
        
    except Exception as e:
        print("\n" + "-"*10 + " Occured Error " + "-"*10)
        print(e) 

if __name__ == "__main__":
    main()
```
---
*new updates are coming...*

