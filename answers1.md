1
--Using chipotle.tsv in the data subdirectory:
$ git clone https://github.com/vybstat/dat9

$ cp dat9/data/chipotle.tsv homework1/data/chipotle.tsv

--Look at the head and the tail, and think for a minute about how the data is structured. What do you think each column means? What do you think each row means? Tell me! (If you're unsure, look at more of the file contents.)
$ head chipotle.tsv
$ tail chipotle.tsv
-----there are 5 columnsin this transactional data, order id, quantity, item_name, choice_desc, price. Each row is a unique transaction, ie an order of a particular item. 
-----There can be several items in the same order.
	

--How many orders do there appear to be?
------1834
--How many lines are in the file?
$ wc chipotle.tsv
------4623
--Which burrito is more popular, steak or chicken?
$ cut -f3 chipotle.tsv | grep "Burrito" | sort | uniq -c | wc
------Chicken

--Do chicken burritos more often have black beans or pinto beans?
$ cut -f3,4 chipotle.tsv | grep "Burrito" | grep "Chicken" | grep "Black Beans" | wc -l
$ cut -f3,4 chipotle.tsv | grep "Burrito" | grep "Chicken" | grep "Pinto Beans" | wc -l
-------282
-------106
------- Black

2.
--Count the number of occurrences of the word 'dictionary' (regardless of case) across all files in the DAT9 repo.
$ grep -r "a" * | wc
------- 2
