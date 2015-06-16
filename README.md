練習問題 9.1

def display():
	fin = open('words.txt')
	for line in fin:
		word = line.strip()
		if(20 <= len(word)):
			print word

以下実行結果

counterdemonstration
counterdemonstrations
counterdemonstrators
hyperaggressivenesses
hypersensitivenesses
microminiaturization
microminiaturizations
representativenesses


練習問題 9.2

def has_no_e(word):
	if("e" in word):
			return False
	return True

def display2():
	fin = open('words.txt')
	a = 0
	t = 0
	for line in fin:
		word = line.strip()
		if(has_no_e(word)):
			print word
			a += 1.0
			t += 1.0
		else:
			a += 1.0
	return t/a*100

文字eを含まない単語は33.073834231%であった。


練習問題 9.3 

def avoids(word,letter):
	for i in word:
		if(i == letter):
			return False
	return True

def display2():
	fin = open('words.txt')
	a = 0
	t = 0
	letter = raw_input()
	for line in fin:
		word = line.strip()
		if(avoids(word,letter)):
			print word
			a += 1.0
			t += 1.0
		else:
			a += 1.0
	return t/a*100

文字aを含まない単語は50.256130886%であった。

練習問題 9.4 

def use_only(word,combination):
	for i in word:
		if(i in combination):
			pass
		else:
			return False
	return True

abcのみで構成される単語は以下の8個であった。
aa
aba
abaca
ba
baa
baba
bacca
cab

練習問題 9.5 

def uses_all(word,combination):
	for i in combination:
		if(avoids(word,i)):
				return False
	return True

全ての母音"aeiou"を使うような単語は598個、"aeiouy"では42個であった。

練習問題 9.6 

def is_abecedarian(word):
	k = 0
	for i in word:
		for j in word[k+1:]:
			if(j < i):
				return False
		k += 1
	return True

この条件を満たす単語は596個
