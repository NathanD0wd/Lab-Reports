# Grep and Its Commands

Written By: Nathan Dowd

---

Hey guys, and welcome back to my blog. This week we're gonna be looking at the grep command. In particular, we'll be diving into the additional commands you can add on to grep and what each of them do. To start, I asked [ChatGPT](https://chat.openai.com/chat), "What are all the additional commands grep has?" This gave me a list of ten add-ons that can change how output is displayed by grep. We're only gonna be looking at four of these though. Those being: '-i' or '--ignore-case' , '-v' or '--invert-match' , '-c' or '--count' , and '-o' or '--only-matching'. We will also be using the '-r' command, but not as one of our four examples. We are just using this to recursively search through all the files in our directory so we don't have to list which ones we would like to search. The directory we will be searching is this [GitHub Page](https://github.com/ucsd-cse15l-w23/skill-demo1-data), which contains the written-2/ directory, which in turn contains many more files.

In the following examples I will be adding an asterisk on each side of the search word to help you see where it was found in the text.

To start, lets look at '-i'. This command tells grep to search for the specified word, regardless of case. 

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:319$ grep -r -i 'lucayans'
written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of 
Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled 
in the Bahamas. Originally from South America, they had traveled up through the 
Caribbean islands, surviving by cultivating modest crops and from what they caught 
from sea and shore. Nothing in the experience of these gentle people could have prepared 
them for the arrival of the Pinta, the Niña, and the Santa Maria at San Salvador on 
12 October 1492. Columbus believed that he had reached the East Indies and mistakenly 
called these people Indians. We know them today as the *Lucayans*. Columbus claimed the 
island and others in the Bahamas for his royal Spanish patrons, but not finding the gold 
and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle 
in the Bahamas, but the number of shipwrecks attest that their galleons frequently passed 
through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home 
ports. On Eleuthera the explorers dug a fresh-water well —at a spot now known as “Spanish 
Wells” — which was used to replenish the supplies of water on their ships before they began 
the long journey back to Europe with their cargoes of South American gold. As for the 
*Lucayans*, within 25 years all of them, perhaps some 30,000 people, were removed from the 
Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on 
Hispaniola (Haiti), Cuba, and elsewhere in the Caribbean.
```

In this example, we can see that we were searching for the word 'lucayans'. But the results we got contained the word 'Lucayans'. This is because '-i' made grep ignore the case of the characters and returned any 'lucayans' it found.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:326$ grep -r -i 'whoever'
written_2/non-fiction/OUP/Fletcher/ch5.txt:*Whoever* sheds man’s blood by man shall 
his blood be shed;
written_2/non-fiction/OUP/Fletcher/ch6.txt:If the analogy with common law monopolies 
had held, the second problem would then have consisted of transplanting the English 
practice of invalidating statutes simply because they violated, as Edward Coke said in 
another leading case, “common right or reason.”15 There was no evidence that courts in 
the United States would or could invalidate statutes simply because they violated the 
“common law.” The Supreme Court never took this attack on the Louisiana statute seriously. 
It interpreted Coke’s decision in the Case of Monopolies to be about whether the king 
could grant a monopoly. Coke supposedly took the side of the Commons against the king, 
but left open the question whether parliament could grant monopolies. The impermissibility 
of the statute is dismissed with the rhetorical question: “*Whoever* doubted the authority 
of Parliament to change or modify the common law?”16 The notion of legislative power to 
regulate the economy prevailed. The elected representatives of the people enjoyed 
wide-ranging discretion in the legislature to enact measures that had at least the nominal 
purpose of promoting the public good.
written_2/travel_guides/berlitz1/HistoryMadeira.txt:*Whoever* first stepped ashore on 
Madeira discovered no signs
written_2/travel_guides/berlitz2/Athens-History.txt:In ancient Greek mythology Athens is 
named following a contest between Athena, goddess of wisdom, and Poseidon, god of the sea. 
Both had their eye on the prize real estate, so it was agreed that *whoever* could come 
up with the more useful gift for mortals would win. The half-human, half-serpent king of 
Athens, Cecrops, acted as arbiter. 
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:Next to the fort is the pretty 
Legislature building with a classical façade painted bright lime green. Finished in 1874, 
the building was originally used as a barracks for troops based at the fort. Behind the 
fort and the Vendors Plaza is Emancipation Park, perhaps the one place in town where you 
can sit in the shade of the trees and enjoy the cooling sea breeze after your sightseeing 
and shopping. The park was named to commemorate the freeing of the slaves in 1848. Across 
Tolbod Gade is the Tourist Information Office, where you can pick up maps and other 
information. On the northern corner of Tolbod Gade is the main post office. Make your way 
in that direction, but don’t be tempted to turn right and head for the stores just 
yet. Take the steps to Kongens Gade, which is the street behind the Lutheran Church. 
The steps climb onto the steep hill that has many of the oldest and most important 
buildings of Danish Charlotte Amalie. The family houses of the merchants and civil 
servants where built high on this rise — named Government Hill — to take advantage of 
the cooling breeze. Kongens Gade itself has several buildings dating back to the late 18th 
and early 19th centuries. Hotel 1829, named for the year in which it was built, sits amid 
other fine homes. Walk past Hotel 1829 and pause at the steps beside it, which climb higher 
onto Government Hill. These are the 99 Steps, one of a series built by the Danes in the mid 
1700s to allow pedestrian access to the town below. The 99 Steps are the longest in town, 
but *whoever* named the flight must have become tired toward the end and miscounted — 
there are in fact 103.
```

In this example, I was searching for the word 'whoever'. If I had not used '-i', several results would have been left out. This command is useful for if you aren't sure whether or not a word is capatilized or to find all cases of common words, even if they are capitalized at the start of a sentence.

Now, lets look at '-v'. This command returns the results without the given string. For this, we will not be using the '-r' command.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:336$ grep -v 'the' written_2/travel_guides/berlitz1/HandRIbiza.txt

        Recommended Hotels
        The establishments listed below offer a cross-section of
        island comes with chips (french fries).
        offfical government rating system.
        expect to pay for a three-course meal for two, excluding wine, tax and
        ✪less than 5,000 ptas.
        ✪✪5,000–8,000 ptas.
        ✪✪✪more than 8,000 ptas.
```

In this, we are searching the file HandRIbiza.txt for lines that do not contain 'the'. As you can see 'The' is still included, but not any 'the'.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:338$ grep -v 'c' written_2/non-fiction/OUP/Castro/chY.txt

Yard Shrines
Yardas (Gardens)
Yo Soy Joaquin
See I Am Joaquin/Yo Soy Joaquin
```

Now, we are searching the Castro/chY.txt file for lines without the character 'c'. This command can be very useful for a number of reasons. If you mark certain lines or files with a certain symbol to mark them as checked/completed, you could use this command on that symbol to see the remaining lines.

Now lets look at the '-c' command. This prints a count of the lines that match your search.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:345$ grep -c 'the' written_2/travel_guides/berlitz1/WhereToItaly.txt
2684
```

Now we are searching for 'the' in the file WhereToItaly.txt. However, as you can see by the result, only the amount of times 'the' shows up in a line is shown.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:346$ grep -c 'e' written_2/travel_guides/berlitz1/WhereToItaly.txt
4067
```

In this, we are searching how many times 'e' shows up in lines in WhereToItaly.txt. This command is very useful as it shows you how many times it appears without filling your screen with all 4,000 lines of output. When searching for words that are very common in large files or directories, this is nice so you aren't overwhelmed with output.

Last, but not least, we will be using '-o'. This prints only the matching part of the line containing the word you are searching for.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:348$ grep -o -r 'Lucayans'
written_2/travel_guides/berlitz2/Bahamas-History.txt:Lucayans
written_2/travel_guides/berlitz2/Bahamas-History.txt:Lucayans
```

We can see that this command is very similar to one I used in an earlier example. But this time, the output is so much neater. Only the word we are searching for is shown, and we can see it appears twice in Bahamas-History.txt.

```
[cs15lwi23ati@ieng6-202]:skill-demo1-data:350$ grep -o -r 'beans'
written_2/non-fiction/OUP/Castro/chB.txt:beans
written_2/non-fiction/OUP/Castro/chB.txt:beans
written_2/non-fiction/OUP/Castro/chO.txt:beans
written_2/non-fiction/OUP/Castro/chP.txt:beans
written_2/travel_guides/berlitz1/WhatToIbiza.txt:beans
written_2/travel_guides/berlitz1/WhatToIbiza.txt:beans
written_2/travel_guides/berlitz1/WhatToIbiza.txt:beans
written_2/travel_guides/berlitz1/WhatToIstanbul.txt:beans
written_2/travel_guides/berlitz1/WhatToItaly.txt:beans
written_2/travel_guides/berlitz1/WhatToJamaica.txt:beans
written_2/travel_guides/berlitz1/WhatToJamaica.txt:beans
written_2/travel_guides/berlitz1/WhatToJapan.txt:beans
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt:beans
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt:beans
written_2/travel_guides/berlitz2/Canada-History.txt:beans
written_2/travel_guides/berlitz2/Cancun-History.txt:beans
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:beans
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:beans
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt:beans
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt:beans
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:beans
```

Now, I'm searching for all the times 'beans' shows up in written-2/. As you can see, the -o command is invaluable for helping you locate which files contain the word 'beans', which is life-changing information. You could also use it for other things, but usually just to find 'beans'.

Thanks for joining me again on my biweekly blog:). Hope you learned something valuable.

-Nathan
