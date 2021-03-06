<!--
 * @Author: Caspar
 * @Date: 2019-11-05 16:07:54
 * @LastEditors: Caspar
 * @LastEditTime: 2019-11-05 17:35:04
 * @Description: file content
 -->
# PyNERER 
A modified version of the Project [PyNER](https://github.com/dat/pyner)   
I changed the project name for that the lib can't be used with the same name and version of the former one. Or you will meet this issue:  
```
        -------------------------------------------------------------------
        ZipImportError                            Traceback (most recent call last)
        ~/work/soupus_papers/code/test_ner.py in 
        ----> 1 import ner  
        ZipImportError: bad local file header: '/Users/channel/anaconda3/lib/python3.6/site-packages/ner-0.1-py3.6.egg'
```
This project PyNER is the Python interface to the [Stanford Named Entity Recognizer](https://github.com/dat/stanford-ner).

## Project Homepage

* [Stanford Named Entity Recognizer](http://nlp.stanford.edu/software/CRF-NER.shtml)

## Installation

    $ python setup.py install

You can record the packages you have installed by adding these paraneters 

    $ python setup.py install --record install.txt

## Basic Usage
    
    >>> import nerer
    >>> tagger = nerer.HttpNER(host='localhost', port=8080)
    >>> tagger.get_entities("University of California is located in California, United States")
    {'LOCATION': ['California', 'United States'],
     'ORGANIZATION': ['University of California']}
    >>> tagger.json_entities("Alice went to the Museum of Natural History.")
    '{"ORGANIZATION": ["Museum of Natural History"], "PERSON": ["Alice"]}'

Remember that, if you are running the local server deployed on localhost, the default url of the page is _http://localhost:8080/_. then you have to add another parameter __location='/ner'__ in the function __HttpNER()__  

    >>> tagger = nerer.HttpNER(host='localhost', port=8080, location='/ner')

## Online Demo

* [Graphical demo of several models](http://nlp.stanford.edu:8080/ner/)

## License

BSD License

## Author

PyNER is developed by maintained by Dat Hoang.
It can be found here: http://github.com/dat/pyner

PyNERER is updated from PyNER by Casper Chan in order to solve some issues.
It can be found here: https://github.com/channel960608/pynerer

