This python code can be used to crack Sha 256 algorithm but please notice that this code is just for numbers range in 1 to 1000 and you must create an exel file with four character name and number then import it to the python file. Finally run the program and enjoy ;)
ps: i add the code in here.
import csv
import hashlib
my_dict = {}
hash_dict = {}
for num in range(1000, 10000):
    num_str = str(num)
    hashed_num = hashlib.sha256(num_str.encode()).hexdigest()
    hash_dict[hashed_num] = num
with open("pap.csv") as fhand:
    text = csv.reader(fhand)
    for row in text:
        my_dict[row[0]] = row[1]
search_hash = my_dict.get("char1")
if search_hash in hash_dict.keys():
    password = hash_dict[search_hash]
    print("char1 is", password)
else:
    print("noting found.")
search_hash = my_dict.get("char2")
if search_hash in hash_dict.keys():
    password = hash_dict[search_hash]
    print("char2 is", password)
else:
    print("noting found.")
search_hash = my_dict.get("char3")
if search_hash in hash_dict.keys():
    password = hash_dict[search_hash]
    print("char3 is", password)
else:
    print("noting found.")
search_hash = my_dict.get("char4")
if search_hash in hash_dict.keys():
    password = hash_dict[search_hash]
    print("char4 is", password)
else:
    print("noting found.")
