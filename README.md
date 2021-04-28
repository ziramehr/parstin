# About Pārstin
Pārstin is the name proposed by Iranian Astronomer, Astrophysicist and Linguist Dr. Mohammad Heydari-Malayeri for an alternative writing system for the Persian language (Pārsi), resembling the Latin script. It has several advantages over the current script (let's call it farsi writing) which is adapted from Arabic, most importantly, it's precision in capturing Pārsi. Moreover, Pārsi is an Indo-European language which means that it has more commonalities with Latin than with Arabic. 
The proposed writing system was justified and explained in detail by Iranian Philosopher and Translator Dr. Mir Shamsuddin Adib-Soltani in _An introduction to the writing of the Persian script._ Amirkabir Publications, Tehran, 1976. A summary of the outcomes is available in the below infographic thanks to Dr. Heydari-Malayeri. This project started under the influence of a series of his talks titled "Persian Writing" ([available on youtube since Oct 2018.](https://www.youtube.com/watch?v=t2P8ou7p2nk&list=PLuhW6Hw2wheOjqD5m-qmxI01Ky3d0v5nF))

![image](https://user-images.githubusercontent.com/83266560/116194068-2eedf380-a6e5-11eb-825f-b333e2c7c70b.png)

(Source: https://t.me/persianmalayeri/1738)

## Objective
The primary objective here is to provide the public with free tools for seamlessly converting digitized Persian literature and documents from the common Arabic script to Pārstin script.

## Value proposition
Dr. Heydari Malayeri mentions the following points as two of the values in changing the writing system to Pārstin:


1- "Equipping Pārsi with the alphabet which is compatible with the language."


2- "A cultural excitation, or trigger, for associating Iranians with methodology and precision in thinking."


It's thrilling that with this project's success we get one step closer to these values.

# Design
## Initial Design
I came up with the following initial design. Feedbacks are encouraged and appreciated.
![image](https://user-images.githubusercontent.com/83266560/116226851-573b1980-a708-11eb-8ed6-6673594a14c0.png)

# Present Farsi Handwriting OCR (Optical Character Recognition)
For this process, a good approach might be to first evaluate the existing farsi OCRs and if the performance was not satisfactory (close to perfect) we need to create a better OCR tool. Here are some ideas that I can imagine being helpful: 1- Take advantage of the common textual fonts as well as [the wealth of the novel fonts resembling handwriting](https://maryamsoft.com/FontShop/) that has recently become available, thanks to the creative work of iranian typographers, for creating training datasets. This way OCR will more likely be effective for handwritings as well as texts. 2- Take advantage of Image Augmation methods such as imgaug for adding various noise, rotation and warping effects to the dataset. 3- Use the database of classical Persian literature available from [Ganjoor](http://epub.ganjoor.net/) for creating the dataset.

# Pārsi phonetic language model
A survey needs to be conducted to find the available Open Source language models and their utility. But most likely we need to develop our own:
At least, we require to have, a comprehensive dataset of phonetics for each persian word. This can be saught in electronic Dictionaries, and Encyclopedias which provide phonetics for words in farsi writing system. At this time, the only resource that I could identify with similar data (Pārstin instead of phonetics) is the [Etymological Astronomy and Astrophysics Encyclopedia by Dr. M. Heydari-Malayeri](http://dictionary.obspm.fr/index.php).

Eventually the language model should be evolved to recognize which [heteronym/heterophone](https://en.wikipedia.org/wiki/Heteronym_(linguistics)) to interpret based on the context.
## An ongoing survey of the existing language models
Google translate: does not provide text-to-speech for sentences in persian. 
[Ariana text-to-speech](http://farsireader.com/webdemoen/): I could identify that this tool is capable of converting simple sentences to speech, so it can derive some of the unwritten phonetic information but as the complexity increases mistakes become prevalent to the point that it barely works for poetry. Also it not an open source application. 
## Coverting phonetics to Pārstin
This step seems to have the least amount of complexity as there is a one-to-one mapping between the phonemes in Pārsi and the Pārstin alphabet.

## First challenges: Unwritten phonemes 
The "-e" and "-ye" in the middle of a noun compund.
### Solutions for predicting the unwritten phonemes
This information is almost always absent from the present farsi writing. 1- A web extension that overlays text with Parstin can add an optional -e or -ye at the end of such noun compounds so people can choose the correct pronunciation based on the context. 2- A website can provide readers with short excerpts from literature written in both writing systems and provide them with tools to correct the Pārstin text.
