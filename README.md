# About
This project started under the impetus of a series of lectures by Dr. M. Heydari Malāyeri titled "Persian Writing" ([available on youtube since Oct 2018.](https://www.youtube.com/watch?v=t2P8ou7p2nk&list=PLuhW6Hw2wheOjqD5m-qmxI01Ky3d0v5nF))
For the time being this page is the single document capturing the software design specifications and tracking the developments. It also includes linguistic insights which drive the design and development. As we progress, some of the information will migrate to designated websites and wiki pages to make this page shorter. Some of the features described here may also migrate to designated repositories.
# What is Pārstin?
Pārsi, also known as Persian or Fārsi, [is a Western Iranian language belonging to the Iranian branch of the Indo-Iranian subdivision of the Indo-European languages](https://en.wikipedia.org/wiki/Persian_language). The Present Pārsi Writing System (PPWS) resembles Arabic writing. Pārstin is the name proposed by Iranian Astronomer, Astrophysicist and Linguist Dr. Mohammad Heydari-Malayeri for an alternative writing system for Pārsi, which resembles the Latin transcription. It has significant advantages and improvements to offer over PPWS.
The proposed writing system (Pārstin) was justified and explained in detail, after an in-depth analysis by Iranian Philosopher and Translator Dr. Mir Šamsoddin Adib-Soltāni in his book: "Darāmad-i bar cegunegi-ye šive-ye xatt-e fārsi" _An Introduction to Problems of Persian Orthography._ Amirkabir Publications, Tehran, 1976. Thanks to Dr. M. Heydari-Malayeri for preparing the following infographic showing the new alphabet. 

![image](https://user-images.githubusercontent.com/83266560/116194068-2eedf380-a6e5-11eb-825f-b333e2c7c70b.png)

(Source: https://t.me/persianmalayeri/1738)

# Objectives
## Converting content from PPWS to Pārstin
The primary objective here is to provide the public with free tools for seamlessly converting digitized Persian literature, documents and webcontent from the common Arabic script to Pārstin script.
## Strech goal
Recommending Pārsi equivalents for the words, in the rendered text, that come from other languages.

# Value proposition
According to Dr. M. Heydari-Malayeri, here are two promises of changing the writing system to Pārstin:


1- "Equipping Pārsi with the alphabet which is compatible with the language."


2- "A cultural excitation, or trigger, for associating Iranians with methodology and precision in thinking."


It's thrilling that with this project's success we can get one step closer to such values.

# Design
## Initial Design
I came up with the following initial design. Feedbacks are encouraged and appreciated.
![image](https://user-images.githubusercontent.com/83266560/116226851-573b1980-a708-11eb-8ed6-6673594a14c0.png)

# Present Pārsi Handwriting OCR (Optical Character Recognition)
For this process, a good approach might be to first evaluate the existing farsi OCRs and if the performance was not satisfactory (close to perfect) we need to create a better OCR tool. Here are some ideas that I can imagine being helpful: 1- Taking advantage of the common textbook fonts as well as [the wealth of the novel fonts resembling handwriting and calligraphy](https://maryamsoft.com/FontShop/) that has recently become available, thanks to the creative work of iranian typographers, to creating training datasets. This way the OCR will more likely be effective for handwritings as well as texts. 2- Take advantage of Image Augmation methods such as imgaug for adding various noise, rotation and distortion effects to the dataset. 3- Use the database of classical Persian literature available from [Ganjoor](http://epub.ganjoor.net/) for creating the dataset.

A quick test of Google Translate's handwriting input for Pārsi shows promising results. However, it is not Open Source, therefore we cannot rely on it for Pārstin. 

# Pārsi phonetic language model
A survey needs to be conducted to find the available Open Source language models and their utility. But most likely we need to develop our own:
At least, we require to have, a comprehensive dataset of phonetics for each persian word. This can be saught in electronic Dictionaries, and Encyclopedias which provide phonetics for words in farsi writing system. At this time, the only avialble resource that I could locate with similar data (Pārstin instead of phonetics) is the [Etymological Astronomy and Astrophysics Encyclopedia by Dr. M. Heydari-Malayeri](http://dictionary.obspm.fr/index.php).

Eventually the language model should be evolved to recognize which [heteronym/heterophone](https://en.wikipedia.org/wiki/Heteronym_(linguistics)) to interpret based on the context.
## An ongoing survey of the existing language models
Google translate: does not provide text-to-speech for sentences in PPWS. 
[Ariana text-to-speech](http://farsireader.com/webdemoen/): I could determine that this tool is capable of converting simple sentences to speech, so it can derive some of the unwritten phonetic information but as the complexity increases mistakes become prevalent to the point that it barely works for poetry. Also it is not an open source application. 
## Coverting phonetics to Pārstin
This step seems to have the least amount of complexity as there is a one-to-one mapping between the phonemes in Pārsi and the Pārstin graphemes.

## Challenges
### Unwritten phonemes 
For example, he "-e" and "-ye" in the middle of a noun compound.
#### Solutions for predicting the unwritten phonemes
Such information is almost always absent from the present farsi writing, and added in the minds of the reader. Therefore, we need to populate a database from the users' input for training the model for this purpose. Two approaches come to mind at the initial stage when the database is so small that the Pārstin conversion is still unreliable. 1- A web extension that overlays text with Parstin can add an optional -e or -ye at the end of such noun compounds so people can make the correct choice based on the context. 2- A website can provide readers with short excerpts from literature written in both writing systems and provide them with tools to correct the Pārstin text.
### Orthography of -i and -yi at the end of non-specific or non-particular nouns
### Orthography of -hā at the end of plural nouns
### Graphemes for Hamze and Ein
### Distinguishing between v and w
They share the same letter in PPWS.

## Typing in Pārstin (Input Methods)

**Linux (Ubuntu):** all the special characters in the Pārstin alphabet can be entered through the definition and use of the [Compose](https://help.ubuntu.com/stable/ubuntu-help/tips-specialchars.html.en) key.

**Android (G-board), MacOS, iOS:** all the special Pārstin characters are accessible by long-pressing the corresponding letter (e.g z for ž, and a for ā) on the key board.

**Windows 10 - after 2019** the special characters can be found in the Emoji Panel (WindowsKey + . ).
