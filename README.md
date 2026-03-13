# Geoguessr Linguistic Data Analysis

Geoguessr is a game based on Google Street View that places the player on a random place in the world and asks him to guess the precise location on a map. One of the clues that helps the plyaer find the right location is the language used on signs and billboard.

This repository contains a series of language-based dashboards and data analysis relevant for this game.

<h2>Table of content</h2>
<ol type="1">
<li><a href="https://github.com/Surlet/Linguistic-Data-Analysis/tree/main#dashboard-for-the-cyrillic-script">Cyrillic Script Dashboard</a></li>
</ol>

<h2>Cyrillic Script Dashboard</h2>

<h3>Introduction</h3>

The objective of this dashboard is to give the user an overview of the 55 different Cyrillic letters and their use in the various languages.

<h3>Skills used</h3>
<ul>
  <li>Power Query (ETL)</li>
  <li>Data Cleaning</li>
  <li>M language</li>
  <li>Table</li>
</ul>

<h3>Process</h3>

<h4>1. Extraction</h4>

The data was retrieved from the Wikipedia pages of each language, which always contains a table with every letter used in the alphabet.

<img width="853" height="509" alt="image" src="https://github.com/user-attachments/assets/dcf4957b-9438-44fd-9de5-a5d0d52f2323" />

<h4>2. Transform</h4>

The extracted data for each query was cleaned in order to make it consistent and comparable

<ol type="a">
  <li>Unnecesarry columns were removed, the remaining columns were appropriatly renamed and the format of the "Letter-column" was cleaned adapted where needed to make it consistent.</li>
  <li>A "Language" column was added in each query, specifying the language of the query for each letter</li>
  <li>A Vowel or Consonant column was added, which specifies whether the letter is a vowel or a consonant, using an if-statement in the M-language. A third category, "Modifier sign" was added for the characters "ь" and "ъ"</li>
</ol>

<img width="1379" height="120" alt="image" src="https://github.com/user-attachments/assets/f92bffae-bd81-4915-b2a7-af8ce7e7e1fa" />

<h4>3. Combining the tables</h4>

A Combined Alphabet query was created, merging all the individual language queries. Some additional steps were needed in this process:

<ol type="a">
  <li>The query was grouped by letter</li>
  <li>A Languages column was added, concatenating (separated by a comma) all the languages that use each letter. </li>
  <li>When a letter is used by all 8 languages, the value in the Languages column was replaced with "All languages"</li>
  <li>The Vowel or Consonant column was also added.</li>
</ol>

<img width="690" height="301" alt="image" src="https://github.com/user-attachments/assets/6ee559df-0f5b-43ed-a3e3-8ac4334973b2" />

<h5>4. Load</h5>

The data was loaded into a table. Two slicers were added to give the user the possibility to filter between languages and vowels or consonants. This dashboard gives a clear overview of every Cyrillic letter in use. 

<img width="1053" height="668" alt="image" src="https://github.com/user-attachments/assets/798c1b93-52e0-4eda-a9e9-1ef0e90749c3" />


