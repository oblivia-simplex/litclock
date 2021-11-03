#! /usr/bin/env python3

import json
import random
from datetime import datetime
import os 

DIR = os.path.dirname(os.path.realpath(__file__))

def time_path():
    now = datetime.now()
    stem = now.strftime("%H_%M")
    path = f"{DIR}/times/{stem}.json"
    return path


def get_entry():
    path = time_path()
    try:
        with open(path, "r") as fd:
            j = json.load(fd)
            return j
    except Exception as e:
        print(f"ERROR: {e}")


def pick_entry():
    return random.choice(get_entry())


def md_time():
    e = pick_entry()
    return f"""
{e['quote_first']}**{e['quote_time_case']}**{e['quote_last']}

-- *{e['title']}*, by {e['author']}

"""


if __name__ == '__main__':
    print(md_time())
