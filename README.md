# Geoguessr Linguistic Data Analysis

This is a repository including different linguistic data analysis useful for the online game "Geoguessr". Geoguessr is a game based on Google Street View that puts the player on a random place in the world (as it is covered by Google Street View) and asks him to guess the precise location on a map. The player can use different clues to guess the right location, such as the position of the sun, the vegetation or architecture. One important clue can be the language used on official or non-official signs. As a result, being able to recognise a language is a key skill in the game. 

As a linguist, polyglot and former translator, I want to help the gamers improve their language recognition skills. And if my background gives me a lot of ressources, I also wanted to base my advice on solid linguistic data analysis. In this repository, you can find my work.

<h2>Dashboard for the Cyrillic script</h2>

The first request I received was a coaching session about distinguishing languages that use the Cyrillic script. There are 8 countries covered in Geoguessr that predominently use the Cyrillic script: Serbia, North Macedonia, Bulgaria, Ukraine, Russia, Kazakhstan, Kyrgyzstan and Mongolia, each having their own official languages. These 8 languages do sometimes use distinctively unique letters, and knowing those letters is the easiest way to recognise it. 

In order to learn those letters easily, I have build a dashboard that includes all 55 letters present in at least one language, with different ways to filter the overview.

For every language, the alphabet table from Wikipedia was imported into Excel with PowerQuery. Each query was then cleaned, using the following steps:
<ol type="a">
  <li>Unnecesarry columns were removed, only these columns were kept: Letter; IPA-transcription, Common Transliteration; English Equivalent</li>
  <li>Unnecesarry additions in the Letter column were removed</li>
  <li>A "Language" column was added, specifying the language of the query for each letter</li>
  <li>A Vowel or Consonant column was added, which specifies whether the letter is a vowel or a consonant, using an if-statement in the M-language. A third category, "Modifier sign" was added for the characters "ь" and "ъ"</li>
  <li>The format of the Letter column was modified in some queries in order to have a consistent pattern in all queries: {uppercase letter}-{space}-{lowercase letter}</li>
</ol>

A Combined Alphabet query was created, merging all the individual language queries. In this query, the following steps were taken:

<ol type="a">
  <li>The query was grouped by letter</li>
  <li>A Languages column was added, concatenating (separated by a comma) all the languages that use each letter. </li>
  <li>When a letter is used by all 8 languages, the value in the Languages column is replaced with "All languages"</li>
  <li>The Vowel or Consonant column is also added.</li>
</ol>

The cleaning process is done and the query can now be loaded in a table in a spreadsheet. Two slicers were created, allowing the user to filter per language (or group of languages) and/or per vowel/consonant.

This dashboard gives a clear overview of every Cyrillic letter in use. The user can use the slicers to identify letters specific to certain languages and toggle between vowels and consonants.

<img width="1053" height="668" alt="image" src="https://github.com/user-attachments/assets/798c1b93-52e0-4eda-a9e9-1ef0e90749c3" />


