#Grep and Its Commands

Written By: Nathan Dowd

---

Hey guys, and welcome back to my blog. This week we're gonna be looking at the grep command. In particular, we'll be diving into the additional commands you can add on to grep and what each of them do. To start, I asked ChatGPT, "What are all the additional commands grep has?" This gave me a list of ten add-ons that can change how output is displayed by grep. We're only gonna be looking at four of these though. Those being: '-i' or '--ignore-case' , '-v' or '--invert-match' , '-c' or '--count' , and '-o' or '--only-matching'. We will also be using the '-r' command, but not as one of our four examples. We are just using this to recursively search through all the files in our directory so we don't have to list which ones we would like to search. The directory we will be searching is this [GitHub Page](https://github.com/ucsd-cse15l-w23/skill-demo1-data), which contains the written-2/ directory, which in turn contains many more files.

To start, lets look at '-i'. This command tells grep to search for the specified word, regardless of case.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:319$ grep -r -i 'lucayans'
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had
settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest crops and from what they
caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the Pinta, the Niña, and the Santa Maria at San
Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called these people Indians. We know them today as the Lucayans.
Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not finding the gold and other riches he was seeking, he stayed for only two
weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that their galleons
frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the explorers dug a fresh-water well —
at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they began the long journey back to Europe with their
cargoes of South American gold. As for the **Lucayans**, within 25 years all of them, perhaps some 30,000 people, were removed from the Bahamas to work — and die — in
Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

In this example, we can see that we were searching for the word 'lucayan'. But the results we got contained the word
