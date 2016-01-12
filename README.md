###Stackoverflow Users Tag Cloud###
[**Stackoverflow**](http://stackoverflow.com/) has over 5 million users. Users earn reputation and score tag points based on the tags of the questions and answers they involve with. Each user has a tag section under his/her profile page that lists the tag names and the respective counts. The Python scripts in this repository parse and extract the tag names and scores, which could then be fed to [wordcloud module for Python](https://github.com/amueller/word_cloud) to produce a word cloud image with tags being the words and their respective sizes being proportional to the respective scores. Please note that the scripts work with the current (as of Jan 11th, 2016) webpage format used by Stackoverflow for storing user profiles and their tags information.

###Examples###
Stackoverflow's highest reputation user [Jon Skeet](http://stackoverflow.com/users/22656/jon-skeet)'s tag-cloud with the first **`200`** tags being produced using [example_extensive.py](https://github.com/droyed/stackoverflow_tag_cloud/blob/master/example_extensive.py) -

![Screenshot](https://raw.githubusercontent.com/droyed/stackoverflow_tag_cloud/master/examples/TagCloud_extensive_Sketch%20Serif.png)

A minimal Python script to generate a tag-cloud would be -

	from stackoverflow_users_taginfo import taginfo
	from wordcloud import WordCloud

	info = taginfo(22656, num_tags=200)
	WordCloud().generate_from_frequencies(info).to_image().save('output.png')

The output would be something like -

![Screenshot](https://raw.githubusercontent.com/droyed/stackoverflow_tag_cloud/master/examples/TagCloud_minimal.png)


###Requirements###
* Python 2.7.
* Python modules : NumPy, Requests, itertools.
* [BeautifulSoup](http://www.crummy.com/software/BeautifulSoup/) - To extract html information. Works with version 4.4.1, might work with older versions too, but not tested. 
* [Word_cloud](https://github.com/amueller/word_cloud) - Word cloud creation.
