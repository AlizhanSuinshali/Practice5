# 1
import re

def match_ab_zero(text):
    pattern = r'ab*'
    return re.fullmatch(pattern, text) is not None

# 2
def match_ab_range(text):
    pattern = r'ab{2,3}'
    return re.fullmatch(pattern, text) is not None

# 3
def lowercase_underscore(text):
    pattern = r'[a-z]+_[a-z]+'
    return re.findall(pattern, text)

# 4
def upper_then_lower(text):
    pattern = r'[A-Z][a-z]+'
    return re.findall(pattern, text)

# 5
def a_anything_b(text):
    pattern = r'a.*b$'
    return re.search(pattern, text) is not None

# 6
def replace_with_colon(text):
    return re.sub(r'[ ,.]', ':', text)

# 7
def snake_to_camel(text):
    # Matches _ and the following character, captures the character
    return re.sub(r'_([a-z])', lambda x: x.group(1).upper(), text)

# 8
def split_at_uppercase(text):
    # Splits at positions where an uppercase letter is found
    return re.split(r'(?=[A-Z])', text)

# 9
def insert_spaces(text):
    # Finds an uppercase letter and adds a space before it
    return re.sub(r'([A-Z])', r' \1', text).strip()

# 10
def camel_to_snake(text):
    # Finds uppercase and replaces with _ + lowercase
    str1 = re.sub('(.)([A-Z][a-z]+)', r'\1_\2', text)
    return re.sub('([a-z0-0])([A-Z])', r'\1_\2', str1).lower()