# About Pārstin
Pārstin is the name proposed by Iranian Astrophysicist and Linguist Dr. Mohammad Heydari-Malayeri for an alternative writing system for the Persian language (Pārsi), resembling the Latin script. It has several advantages over the current script (let's call it farsi writing) which is adapted from Arabic, most importantly, it's precision in capturing Pārsi. Moreover, Pārsi is an Indo-European language which means that it has more commonalities with Latin than with Arabic. 
The proposed writing system was justified and explained in detail by Iranian Philosopher and Translator Dr. Mir Shamsuddin Adib-Soltani in _An introduction to the writing of the Persian script._ Amirkabir Publications, Tehran, 1976. A summary of the outcomes is available in the below infographic thanks to Dr. Heydari-Malayeri. This project started under the influence of a series of his talks titled "Persian Writing" ([available on youtube since Oct 2018.](https://www.youtube.com/watch?v=t2P8ou7p2nk&list=PLuhW6Hw2wheOjqD5m-qmxI01Ky3d0v5nF))

![image](https://user-images.githubusercontent.com/83266560/116194068-2eedf380-a6e5-11eb-825f-b333e2c7c70b.png)

(Source: https://t.me/persianmalayeri/1738)

## Objective
The primary objective here is to provide the public with free tools for seamlessly converting digitized Persian literature and documents from the common Arabic script to Pārstin script.

## Value proposition
Dr. Heydari Malayeri mentions the following points as two of the values in changing the writing system to Pārstin:


1- "Equipping Pārsi with the alphabet which is compatible with the language."


2- "A cultural excitation, or trigger, for associating Iranians with methodology and precision in thinking."


I hope that this project succeeds in bringing us one step closer to these values.

# Design
![image](https://user-images.githubusercontent.com/83266560/116226851-573b1980-a708-11eb-8ed6-6673594a14c0.png)

## Farsi OCR (Optical Character Recognition)
For this process, a good approach might be to first evaluate the existing farsi OCRs and if the performance was not satisfactory (close to perfect) we have some approaches to try: 1- Take advantage of [the wealth of the novel fonts](https://maryamsoft.com/FontShop/) that has recently become available, thanks to our typographers, for creating datasets. 2- Take advantage of Image Augmation methods such as imgaug for adding various noise, rotation and warping effects to the dataset.

## Parsi phonetic language model
We need access to a dictionary database which provides us with the phonetics for each persian word.
