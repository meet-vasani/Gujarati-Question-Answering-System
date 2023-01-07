# Gujarati-Question-Answering-System

As there are search engines which evolve over time and give you the perfect results but also it comes with the burden of choosing the appropriate page and finding the answer from that particular page. It was essential to design a system, which gives you an accurate result from the given page, given the content and the question. Question Answering systems were built in order to suffice the requirement. The system works based on the content given, and the question is asked accordingly to the content, there are algorithms which works across the content and finds the appropriate answer for the provided question. There are many variations on how one proceed towards the problem. We have first classified our question (What, Where, When, Who/ Whom/ Whose, How Many/ How Much, Which). After classifying, we made algorithms on how to extract answers for that particular question accordingly. There will be certain changes in each algorithm because each question point out to a different context from the content itself. Once we get our answer, we pre – process it and then form a whole sentence using some part of the question and if required we add some parts from the context chosen. There are currently many Question Answering system which are working at its full capacity to fulfil the need, but there are none for the Gujarati language in particular, and as per the norms of different languages, the system has to be made from the scratch for different languages. As Gujarati language has its own rules and applying the English Question Answering System to find answers for the Gujarati context, it will result in a garbage value and will not be a complete solution.

Before the Question Answering Systems, there comes Search Engines, which give you n number of results to choose from based on the given input question. So, eventually, you get a lot of information from which you can choose to select any information you like, but as time is progressing at a faster rate as ever, humans also wants things to happen fast and want answers to questions within millisecond, because we don’t want someone to get ahead of us in terms of knowledge. 

Then, it was time to design something which can give you an accurate answer to the particular question being asked. Humans want to gain knowledge but at the same instance, they don’t want to waste time reading all sorts of long passages and paragraph, all they want is a small short simple answer to a question they are seeking. Yes, Search Engines are necessary to find the right amount of information for the question which someone is seeking, but to find the accurate answer from that information retrieved is to be done by this Question Answering Systems to conserve time. 

There are various Systems out there for all the different languages, but there was none for Gujarati language. All the languages have their own criteria and due to this the approach can be similar but the algorithms for all the different types of Question needs to be changed, otherwise the suitable answer will not be found.

The base to this project is Natural Language Processing, which explicitly means processing any language in order to get an outcome which can ease the users work. There are various prebuilt libraries which make it easy to apply any particular workflow to any project which is deemed to be of worthy to the future. Further on there can be a combination of languages in order to reduce the resources been used to create different Question Answering systems for different languages.

The project is all about designing a Question Answering System in Gujarati language manually by using some important resources which were needed. The System will give back answers when you input a particular type of Question. Now Questions are of many different types (What - શું, Where - ક્યાં, When – ક્યારે, Who/ Whom/ Whose - કોણ, કોને, કોની, કોનો, કોના, કોનું, How Many/ How Much - કેટલી, કેટલા, કેતલુ, કેટલો, Which - કયુ, કયા, કયી, કયો). 

Based on the Question and the Context given, the algorithm forms a right answer by mixing some part of the question and some part of the context where necessary and displays it as an output. 

1.2.	Scope of Project

•	Make a full fledge working Question Answering system for Gujarati language.

•	Input a paragraph and Question as Text.

•	The Question will be classified accordingly whether it is (What - શું, Where - ક્યાં, When – ક્યારે, Who/ Whom/ Whose - કોણ, કોને, કોની, કોનો, કોના, કોનું, How Many/ How Much - કેટલી, કેટલા, કેતલુ, કેટલો, Which - કયુ, કયા, કયી, કયો).

•	The classification is done automatically via the algorithm, once the algorithm understands the Question, it goes inside the specific Question Algorithm to form an appropriate answer.

•	The project currently works only on sentences and not paragraphs.

•	The project has no complexities right now, as it is the first prototype ever build for Gujarati language, and there are currently not enough resources available to add more complexities.

•	Have relied on Indo Wordnet for using the Gujarati dictionary. There is a prebuilt API library built for that.

•	Different other libraries have been used for preprocessing to form the answer, which include nltk and regular expression.

The program starts off with getting an input from the user, the input will be text sentence and question regarding that text. After this the question is been classified, once classified, it will look for that particular algorithm in order to form the answer. Now the specific question algorithms are as follows:

	What Algorithm Pseudo code (શું)

1.	Take a Question string

2.	Take a Sentence string

3.	Break the Question into 2 parts:
X1 = before (શું)
X2 = after (શું)

4.	If X1 == Null:
If “નથી” in Text: Append “ના”before Text | Else: Append “હા” before Text

5.	Else:
Convert X1 by replacing: (“તમારું” to “મારુ”), (“તમે” to “મારે”), (“તમારા” to “મારા”), (“તમારી” to ‘મારી”), (“તુ” to “હું”), (“તને” to “મને”), (“તમને” to “અમને”), (“તારુ” to “મારુ”) and storing it in X1_

6.	Tokenize the Text and find noun using INDOWORDNET API with POSTAGGING (NOUN) and store them in Z

7.	Extract the whole string after the last noun from the Text and store it in U

8.	Append the Answer: X1_ + Z + “ “+ U

9.	Remove the Duplicates

10.	For Example:
Question: તમે શું ખાવા માંગો છો?
Given Paragraph Sentence: મારે એક સફરજન ખાવું છે
Resulting Answer: મારે એક સફરજન ખાવું છે

	Where Algorithm Pseudo code (ક્યાં)

1.	Take a Question string

2.	Take a Sentence string

3.	Break the Question into 2 parts:
X1 = before (ક્યાં)
X2 = after (ક્યાં)
4.	Convert X1 by replacing: (“તમારો” to “મારો”) (“તમારું” to “મારુ”), (“તમે” to “મારે”), (“તમારા” to “મારા”), (“તમારી” to ‘મારી”), (“તુ” to “હું”), (“તને” to “મને”), (“તમને” to “અમને”), (“તારુ” to “મારુ”) and storing it in X1_ else X1_ = None

5.	Tokenize the Text and find noun using INDOWORDNET API with POSTAGGING (NOUN) and store them in Z

6.	Extract the whole string after the last noun from the Text and store it in U

7.	If X1_ == None:
Answer = X1 + Z + “ “ + U
Else:
Answer = X1_ + Z + “ “ + U

8.	Remove the Duplicates

9.	Question: તમે ક્યાં જાવ છો?
Given Paragraph Sentence: હું મંદિર જાઉં છું
Resulting Answer: હું મંદિર જાઉં છું

	When Algorithm Pseudo code(ક્યારે)

1.	Take a Question string

2.	Take a Sentence string

3.	Break the Question into 2 parts:
X1 = before (ક્યારે)
X2 = after (ક્યારે)
4.	Convert X1 by replacing: (“તમારો” to “મારો”) (“તમારું” to “મારુ”), (“તમે” to “મારે”), (“તમારા” to “મારા”), (“તમારી” to ‘મારી”), (“તુ” to “હું”), (“તને” to “મને”), (“તમને” to “અમને”), (“તારુ” to “મારુ”) and storing it in X1_ else X1_ = None

5.	If Date or Time in Text:
Extract Date or Time
Else:
“સોમવારે”, “મંગળવારે”, “બુધવારે”, “ગુરુવારે”, “શુક્રવારે”, “શનિવારે”, “રવિવારે”, “આજે”, “આવતીકાલે”, “ગઇકાલે”, “પરમદિવસે”, “સવારે”, “બપોરે”, “સાંજે”, “રાત્રે”, “મધ્ય રાત્રી એ” in Text, then append in O

6.	Try:
Answer1 = X1 + O + X3
Except:
Try:
d = find_date ()
U = “ “.join (d)
Except:
t = find_time ()
U = “ “.join (t)
If X1_ == None:
Answer = X1 + U + X3
Else:
Answer = X1_ + U + X3

7.	Question: તમારો જન્મદિવસ ક્યારે છે?
Given Paragraph Sentence: મારો જન્મદિવસ મંગળવારે છે
Resulting Answer: મારો જન્મદિવસ મંગળવારે છે

8.	If the Text contains Date or Time, then the resulting answer will add them in the answer as of have added Try and Exception blocks

	Who/ Whom/ Whose Algorithm Pseudo code (કોણ, કોને, કોની, કોનો, કોના, કોનું, કોનાથી)

1.	Take a Question string

2.	Take a Sentence string

3.	Break the Question into 2 parts:
X1 = before (કોણ, કોને, કોની, કોનો, કોના, કોનું, કોનાથી)
X2 = after (કોણ, કોને, કોની, કોનો, કોના, કોનું, કોનાથી)

4.	Convert X1 by replacing: (“તમારો” to “મારો”) (“તમારું” to “મારુ”), (“તમે” to “મારે”), (“તમારા” to “મારા”), (“તમારી” to ‘મારી”), (“તુ” to “હું”), (“તને” to “મને”), (“તમને” to “અમને”), (“તારુ” to “મારુ”) and storing it in X1_ 

5.	Tokenize the Text and find noun using INDOWORDNET API with POSTAGGING (NOUN)

6.	Extract the whole string after the last noun from the Text and store it in U 

7.	Append the Answer : X1_ + Z + “ “+ U

8.	Remove the Duplicates

9.	For Example:
Question: બોસ તરીકે તમે કોને પસંદ કરશો?
Given Paragraph Sentence: અમે અમારા બોસ તરીકે સ્મિત ને પસંદ કરીશું
Resulting Answer: બોસ તરીકે અમે સ્મિત ને પસંદ કરીશું

	How Many/ How Much Algorithm Pseudo code (કેટલી, કેટલા, કેતલુ, કેટલો)

1.	Take a Question string

2.	Take a Sentence string

3.	Break the Question into 2 parts:
X1 = before (કેટલી, કેટલા, કેતલુ, કેટલો)
X2 = after (કેટલી, કેટલા, કેતલુ, કેટલો)

4.	Convert X1 by replacing: (“તમારો” to “મારો”) (“તમારું” to “મારુ”), (“તમે” to “મારે”), (“તમારા” to “મારા”), (“તમારી” to ‘મારી”), (“તુ” to “હું”), (“તને” to “મને”), (“તમને” to “અમને”), (“તારુ” to “મારુ”) and storing it in X1_ else X1_ = None

5.	Using Regular Expression, find all the numbers from the Text

6.	If Regular Expression is not able to find any digits:
U = [“થોડું”, “થોડો”, “થોડુક”, “થોડી”, “થોડિક”, “જરિક”, “વધુ”, “વધારે”, “ટુંક”]

7.	If X1_ == None:
Answer = X1 + “ “ + U + X3
Else:
Answer = X1_ + “ “ + U + X3

8.	Question: પરીક્ષા પૂરી થવામાં કેટલો સમય બાકી છે?
Given Paragraph Sentence: ટુંક સમયમાં પરીક્ષા પૂર્ણ થશે
Resulting Answer: પરીક્ષા પૂરી થવામાં ટુંક સમય બાકી છે

	Which Algorithm Pseudo code (કયુ, કયા, કયી, કયો)

1.	Take a Question string

2.	Take a Sentence string

3.	Break the Question into 2 parts:
X1 = before (કયુ, કયા, કયી, કયો)
X2 = after (કયુ, કયા, કયી, કયો)

4.	Convert X1 by replacing: (“તમારો” to “મારો”) (“તમારું” to “મારુ”), (“તમે” to “મારે”), (“તમારા” to “મારા”), (“તમારી” to ‘મારી”), (“તુ” to “હું”), (“તને” to “મને”), (“તમને” to “અમને”), (“તારુ” to “મારુ”) and storing it in X1_ else X1_ = None

5.	Tokenize the Text and find noun using INDOWORDNET API with POSTAGGING (NOUN) and store them in Z

6.	Extract the whole string after the last noun from the Text and store it in U

7.	if X1_ == None:
Answer = X1 + Z + " " + U
Else:
Answer = X1_ + Z +" "+ U

8.	Question: તમે કયા સ્થળની મુલાકાત લીધી હતી?
Given Paragraph Sentence: મેં સુરત શહેરની મુલાકાત લીધી
Resulting Answer: અમે સુરત મુલાકાત લીધી	



