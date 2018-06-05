---
layout: post
title:  "How to get a tech internship"
categories: intern tech internship summer
excerpt: "
"
---

Redfin
	No

Stripe
	No

Khan
	No

Box
	Yes to interview
	First phone interview
		elevator
		unival
	Second
		Simple call talked about a project I'd done I was proud of


Palantir
	No... FIGHT

Google Software Engineering
	First
		Martian lunar surface
			X's represent obstacles
			?'s represent intrest points
			each day, go to an intrest point and reuturn home
			find best landing pt
	Second
		Return if tree is balanced 

		Design question
			nyc subway question
			unlimited swipe card
			lockout time of 15 mins
	Did not go any further

Airbnb
	No

Dropbox
	So bad
	soda sizes, exact soda count
	ways to do it?
	No

Fiscalnote
	Spoke with VP
		Chill
	hackerrank
		1 hr question
		How many matches of the ^subsets in the string?
		My code ran too long, perhaps better than n^2 sltn?

Mozilla Ateam

Linkedin 
	Phonescreen with HR

	data science
		encode and decode binary tree	
	no


Yelp PM

Yelp Software

Facebook Data

Facebook Software

Goldman

MongoDb

CORE yale
	nontechnical

Bloomberg
	bunch of random questions, noncoding technical
	talked about segfaults
	
Wealthfront
	1
		alg to x^n
		binary search
	2
		about linear regression
		given a bunch of database ops, do intersection of two sets
	no

Two Sigma
	recruiter interview

	next, 3 hour challenge
		coding part, series question: does it match x2 = x1*N + L
		next part, NFL predicition

	t, r^2 vals for linear regression changes
	iterated correlation

	no



Jane St
	uniform sample from binary tree

	"compiler"
		optimize jumps
		short jump if within +-32 of the target
		long jump otherwise

	no

Facebook
	merge from mergesort

	[1,1,4,4,5,5,7,8,8]
	return 7

	edit distance of 1

Square


Twitter
	# analyzing unstructured text, streams of data, elastic search internship, machine learning project using random forest and lasso ridge regression

	Q1. Given a undirected unweighted graph, compute its connected components.

	class Node:
	    __init__(self):
	        self.connected = []

	def conenctedCompontents(nodes):
	    seen = []
	    components = []
	    for node in nodes:
	        if node not in seen:
	            component = []
	            # bfs
	            not_seen  = [node]# queue
	            while not_seen:
	                val = not_seen.pop(0)
	                seen.append(val)
	                component.append(val)
	                for i in val.connected:
	                    if node not in seen:
	                        not_seen.append(i)
	            components.append(component)
	    return components

	'''
	in: 1-2  3-4-5
	out: [[1,2],[3,4,5]]

	seen [1,2,3,4,5]
	components [[1,2],[3,4,5]] 
	component [3,4,5]
	not_seen = []

	12
	3
	'''








	# This is the text editor interface. 
	# Anything you type or change here will be seen by the other person in real time.

	'''

	Prices of a stock for N successive days.
	Assume: we dont start wih any unit.

	Question: When should we buy and when should we sell to maximize profit?
	Question: What is max profit?


	5 2 3 6 1
	min_left [5, 2, 2, 2, 1]
	max_righ [6, 6, 6, 6, 1]
	max_prof [1, 4, 4, 4, 0]
	max profit: argmax (min_left - maxright)
	buy date: argmin (max_prof = max profit)
	sell date: argmax (max_prof = max profit)

	10 15 1 5

	[10, 10, 0, 0]
	[15, 15, 5, 5]
	[5, 5, 5, 5]
	5 + 10 => look for 15

	'''

	def buy_sell_stock (prices):
	    '''
	    '''
	    # Construct min left
	    k = max(prices)
	    min_left = []
	    for i in prices:
	        if i < k:
	            k = i
	        min_left.append(k)

	    # Construct max right
	    k = min(prices)
	    max_right = []
	    for i in reversed(prices):
	        if i > k:
	            k = i
	        max_right.append(k)
	    
	    max_prof = [max_right[i]-min_left[i] for i in range(len(prices))]
	    best_profit = max(max_prof)
	    
	    buy_date = max_profit.find(best_profit)
	    sell_date = max_profit.find(reversed(best_profit))
	    
	    return (best_profit, buy_date , sell_date)
	    


4


	 dictionary 

a-z

_acb

a__
acc
abc
ccc

c < b
a < c



a < b < f
a < c < f

abcf
acbf


{
a: b, f, c
b: f
c: f
f: []
}

abc
acb

{
    
}

def ordering(input_dict):
    '''
    input_dict is a list of words
    '''
    pres_table = DefaultDict(set())
    
    for (i in range(len(input_dict)-1)):
        w1 = input_dict[i].split('')
        w2 = input_dict[i+1].split('')
        learned = False
        for k in range(min(len(w1),len(w2))):
            if (w2[k] != w1[k] and not learned):
                learned = True
                pres_table[w2[k]] = pres_table[w2[k]].add(w1[k])
    
    output = ''
    
    while (pres_table):
        val = find_min(pres_table)
        output = output+val
        del pres_table[val]
    
    return output

def find_min(table):
    for i in table.keys():
        if i not in set(table.values()):
            return i
        
        
    

3


'''
// This is the text editor interface. 
// Anything you type or change here will be seen by the other person in real time.
/*
Question:
 Implement a method to find the lowest common ancester of two given nodes from a binary tree
*/
'''

class Node:
    def __init__(val, right, left):
        self.val = val
        self.right = right
        self.left = left
        
def lowest_common_ancestor(root, node_one, node_two):
    last_node = root
    # bfs
    path_one = path(root, node_one)
    path_two = path(root, node_two)
    intersect = []
    for i in min(len(path_one, path_two)):
        if path_one[i] == path_two[i]:
            intersect.append(path_one[i])
    return intersect[-1]
    
    i = 0
    prev = 0
    while (i < min(len(path_one, path_two))):
        if path_one[i] != path_two[i]:
            return prev
         prev = path_one[i]

def path(root, dest):
    return_path = []
    stack = []
    stack.append(root)
    return_path.append(root)
    
    while(stack):
        tmp = stack.pop()
        return_path.pop()
        return_path.push(tmp)
        if (root==dest)
            return return_path
        if (tmp.left):
            stack.append(tmp.left)
        if (tmp.right):
            stack.append(tmp.right)
            
1
2    3
4,5  6,7


2015  2016 full time

square

def solve(capacities, target):
    '''
        capacities is a list of ints
        target is int
    '''
    state_cache = []
    inital = [0 for i in range(len(capacities))]
    state_list = [(inital, [])]
    def add_to_state_list(new_state, path):
        if new_state in state_cache:
            return
        else:
            state_cache.append(new_state)
            state_list.append((new_state, path))
            
    for it, path in state_list:
        if target in it:
            return (it, path)
        for cup in range(len(capacities)):
            # fill cups
            new_state = it[:]
            new_state[cup] = capacities[cup]
            add_to_state_list(new_state, path + ['Fill ' + str(cup)])
        for cup in range(len(capacities)):
            # empty cups
            new_state = it[:]
            new_state[cup] = 0
            add_to_state_list(new_state, path + ['Empty ' + str(cup)])
        for cup_src in range(len(capacities)):
            for cup_dest in range(len(capacities)):
                if cup_src != cup_dest:
                    # pour into other cup
                    new_state = it[:]
                    dest_space = capacities[cup_dest] - new_state[cup_dest]
                    if new_state[cup_src] >= dest_space:
                        new_state[cup_src] -= dest_space
                        new_state[cup_dest] += dest_space
                    else:
                        new_state[cup_dest] += new_state[cup_src]
                        new_state[cup_src] = 0
                    add_to_state_list(new_state, 
                                      path + 
                  [‘Pour from ' + 
                       str(cup_src) + ' to ' + 
                       str(cup_dest)])

                    # - amount in source
                    # - "space" in destination (capacity - amount)
                    # smaller of those two -> transfer


solution = solve([4, 9], 7)
print "state: "
print solution[0]
print "steps: "
print solution[1]
"""
capacities: 1, 3
target: 2

0, 0
- Fill each one
- Empty each one
- Pour from each into each other


- Fill 1
- Pour 1 -> 0

"""

square phone 2

def numPossibleDecodings(code):
    first = 1
    second = 1
    new = 1
    for i in range(1, len(code)):
        idx = code[i-1:i+1] 
        if idx[-1] == '0':
            new = first 
        elif idx[0] == '0':
            new = second 
        elif int(idx) >= 27:
            new = second
        else:
            new = second + first
        first = second
        second = new
    return new
        

print numPossibleDecodings('123')
print numPossibleDecodings('22522')

print numPossibleDecodings("2") == 1
print numPossibleDecodings("19") == 2
print numPossibleDecodings("3121") == 3
print numPossibleDecodings("21216") == 8
print numPossibleDecodings("786789") == 1
print numPossibleDecodings("20204") == 1
print numPossibleDecodings("2010") == 1
print numPossibleDecodings("110") == 1
print numPossibleDecodings("10120") == 1







bridgewater final round

product management
    improve meeting recorders to improve transparency

software engineering
    theres a phone keypad and chess pieces, and you need to record the number of phone numbers you can create

culture interview
    what are you bad at





awake coding interview
    convert 123456 -> one hundred twenty three thousand, four hundred fifty six





square headquarters interview
rounds 1,2 on phone
round 3
    two paragraphs
        count n unique words
        kth word alphabetically
        all words of length m
round 4
    power sets
    abc -> '' 'a' 'b' 'c' 'ab' 'ac' 'bc' 'abc





google online
def solution(X):
    def clean(line):
        return line.lstrip(' ')
    def depth(line):
        return len(line) - len(clean(line))
    path = []
    out = 0
    lines = X.split('\n')
    for ln in lines:
        path = path[:depth(ln)] + [clean(ln)]
        if clean(ln).endswith(('.jpeg', '.gif', '.png')):
            out = max(out, sum([len(i) for i in path]) + len(path))
    return out
def solution(X):
    x_str = str(X)
    possibles = []
    for i in xrange(len(x_str)):
        new_str = x_str[:i]
        new_str += x_str[i]
        new_str += x_str[i:]
        possibles.append(new_str)
    possible_ints = [int(i) for i in possibles]
    return max(possible_ints)

google in person (4 interviews)
interview 1
- started with coin dynamic programming problem, but saw that I already knew how to do it.
you need to find the maximum subset of a string containting at most n unique characters.
for example ABAACABDE => 7
solution:
    maintian head and tail indicies as well as a table of counts
    O(N) time

interview 2:
you have a sparse spreadsheet
implement:
    get, put remove, getCol, getRow
my solution:
    idk if best
    have table of cols to list of guids, table of rows to guids, and guid to (r, c, value) map

interview 3:
flip number over = original number?

then, generate all numbers where flipped = original
solution: simple dynamic programming
def generate(n):
    if not n:
        return
    first = ['']
    second = ['0', '1', '2', '5', '8']
    while len(second[0]) <= n:
        new_one = []
        for i in ['00', '11', '22', '55', '88', '69', '96']:
            for j in first:
                new_one.append(i[0] + j + i[1])
        first = second
        second = new_one
    return second

interview 4:
kinda weird, design a class interface that takes inputs of ranges and then given a number, returns whether it is in one of the ranges

the final solution required inserting ranges into a sorted list using binary search in log(n) time and looking up if a number is in the range in log(n) time as well



