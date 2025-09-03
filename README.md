
# 1. Tính tổng các phần tử trong danh sách
def sum_list(items):
    return sum(items)

# 2. Tính tích các phần tử trong danh sách
def multiply_list(items):
    result = 1
    for x in items:
        result *= x
    return result

# 3. Lấy số lớn nhất trong danh sách
def max_in_list(items):
    return max(items)

# 4. Lấy số nhỏ nhất trong danh sách
def min_in_list(items):
    return min(items)

# 5. Đếm số chuỗi có độ dài >= 2 và ký tự đầu = ký tự cuối
def match_strings(strings):
    return sum(1 for s in strings if len(s) >= 2 and s[0] == s[-1])

# 6. Sắp xếp danh sách tuple theo phần tử cuối
def sort_last(tuples):
    return sorted(tuples, key=lambda x: x[-1])

# 7. Xóa phần tử trùng lặp trong danh sách
def remove_duplicates(lst):
    return list(set(lst))

# 8. Kiểm tra danh sách rỗng
def is_list_empty(lst):
    return len(lst) == 0

# 9. Sao chép danh sách
def clone_list(lst):
    return lst.copy()

# 10. Từ dài hơn n ký tự
def words_longer_than(words, n):
    return [word for word in words if len(word) > n]

# 11. Kiểm tra phần tử chung
def has_common_member(list1, list2):
    return bool(set(list1) & set(list2))

# 12. Xóa phần tử tại index 0,4,5
def remove_indices(lst):
    return [item for i, item in enumerate(lst) if i not in (0,4,5)]

# 13. Mảng 3x4x6 với *
def generate_3d_array():
    return [[['*' for _ in range(6)] for _ in range(4)] for _ in range(3)]

# 14. Xóa số chẵn
def remove_even_numbers(lst):
    return [x for x in lst if x % 2 != 0]

# 15. Trộn danh sách
import random
def shuffle_list(lst):
    random.shuffle(lst)
    return lst

# 16. Số chính phương 1-30
import math
def square_numbers_1_to_30():
    squares = [x for x in range(1,31) if int(math.sqrt(x))**2 == x]
    return squares[:5] + squares[-5:]

# 17. Kiểm tra tất cả số nguyên tố
def is_prime(n):
    if n < 2: return False
    if n in (2,3): return True
    if n%2==0 or n%3==0: return False
    i=5
    while i*i <= n:
        if n%i==0 or n%(i+2)==0:
            return False
        i+=6
    return True

def all_prime(nums):
    return all(is_prime(x) for x in nums)

# 18. Tất cả hoán vị
from itertools import permutations
def all_permutations(lst):
    return list(permutations(lst))

# 19. Phần khác nhau giữa 2 danh sách
def list_difference(a,b):
    return [x for x in a if x not in b], [x for x in b if x not in a]

# 20. Truy cập index
def index_with_values(lst):
    return list(enumerate(lst))

# 21. Chuyển list ký tự thành chuỗi
def chars_to_string(chars):
    return ''.join(chars)

# 22. Tìm index phần tử
def safe_index(lst, item):
    try:
        return lst.index(item)
    except ValueError:
        return -1

# 23. Làm phẳng danh sách nông
def flatten_shallow(nested):
    return [item for sub in nested for item in sub]

# 24. Nối list1 vào list2
def append_list_to_second(list1, list2):
    result = list2.copy()
    result.extend(list1)
    return result

# 25. Chọn ngẫu nhiên phần tử
def random_choice(lst):
    return random.choice(lst)

# 26. Kiểm tra circular identical
from collections import deque
def circularly_identical(a,b):
    if len(a)!=len(b): return False
    dq=deque(a)
    for _ in range(len(a)):
        if list(dq)==b:
            return True
        dq.rotate(1)
    return False

# 27. Số nhỏ thứ hai
def second_smallest(lst):
    uniq = sorted(set(lst))
    if len(uniq)<2:
        raise ValueError("Không có số nhỏ thứ hai.")
    return uniq[1]

# 28. Số lớn thứ hai
def second_largest(lst):
    uniq = sorted(set(lst), reverse=True)
    if len(uniq)<2:
        raise ValueError("Không có số lớn thứ hai.")
    return uniq[1]

# 29. Lấy giá trị duy nhất theo thứ tự
def unique_preserve_order(lst):
    seen=set()
    out=[]
    for x in lst:
        if x not in seen:
            seen.add(x)
            out.append(x)
    return out

# 30. Đếm tần suất
from collections import Counter
def element_frequency(lst):
    return dict(Counter(lst))

# 31. Đếm phần tử trong khoảng
def count_in_range(lst, low, high):
    return len([x for x in lst if low <= x <= high])

# 32. Kiểm tra chứa sublist
def contains_sublist(lst, sub):
    n=len(sub)
    for i in range(len(lst)-n+1):
        if lst[i:i+n]==sub:
            return True
    return False

# 33. Sinh tất cả sublists
def all_sublists(lst):
    subs=[]
    for i in range(len(lst)+1):
        for j in range(i+1, len(lst)+1):
            subs.append(lst[i:j])
    return subs

# 34. Sàng Eratosthenes
def sieve_of_eratosthenes(n):
    primes=[True]*(n+1)
    primes[0:2]=[False,False]
    for i in range(2,int(n**0.5)+1):
        if primes[i]:
            for j in range(i*i,n+1,i):
                primes[j]=False
    return [i for i,p in enumerate(primes) if p]

# 35. Nối list với range
def concat_list_with_range(lst, n):
    result=[]
    for item in lst:
        for i in range(1,n+1):
            result.append(f"{item}{i}")
    return result

# 36. Gán biến động
def assign_variable(name, value):
    globals()[name] = value
    return f"Đã tạo biến '{name}' với giá trị: {value}"

# 37. Phần tử chung trong 2 list
def common_items(list1, list2):
    return list(set(list1) & set(list2))

# 38. Đổi vị trí mỗi phần tử thứ n
def change_position(lst, n):
    lst[n-1::n], lst[n::n] = lst[n::n], lst[n-1::n]
    return lst

# 39. Ghép list số thành integer
def list_to_integer(nums):
    return int(''.join(map(str, nums)))

# 40. Tách danh sách theo chữ cái đầu
from collections import defaultdict
def split_by_first_char(words):
    groups=defaultdict(list)
    for w in words:
        if w:
            groups[w[0].lower()].append(w)
    return dict(groups)

# 41. Tạo nhiều danh sách
def create_multiple_lists(n):
    return [[] for _ in range(n)]
def create_named_lists(names):
    return {name:[] for name in names}

# 42. Tìm thiếu và dư
def missing_and_additional(a,b):
    a_set,b_set=set(a),set(b)
    return list(a_set-b_set), list(b_set-a_set)

# 43. Unpack list
def unpack_list(lst):
    a,b,c = lst
    return a,b,c

# 44. Chia nhóm 5 phần tử
def groups_of_five(lst):
    return [lst[i:i+5] for i in range(0,len(lst),5)]

# 45. Chuyển cặp giá trị thành array duy nhất
def pairs_to_sorted_unique_array(pairs):
    flat=[x for pair in pairs for x in pair]
    return sorted(set(flat))

# 46. Phần tử vị trí lẻ
def odd_index_items(lst):
    return lst[1::2]

# 47. Chèn phần tử trước mỗi phần tử
def insert_before_each(lst, elem):
    out=[]
    for x in lst:
        out.extend([elem,x])
    return out

# 48. In danh sách lồng nhau
def print_nested_lists(nested):
    for sub in nested:
        print(sub)

# 49. Danh sách thành list dictionary
def lists_to_dicts(names, codes):
    return [{'color_name':n, 'color_code':c} for n,c in zip(names, codes)]

# 50. Sắp xếp list dictionary lồng nhau
def sort_nested_dicts(data, key):
    return sorted(data, key=lambda x: x[key])
