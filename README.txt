== Wikipedia Biography Dataset ==

This dataset gathers 728,321 biographies from wikipedia. It was used in our
work,

Text Generation from Structured Data with Application to the Biography Domain
Rémi Lebret, David Grangier and Michael Auli, EMNLP 16,
http://arxiv.org/abs/1603.07771

This publication provides further information about the data and we kindly ask
you to cite this paper when using the data. The data was extracted from the
English wikipedia dump (enwiki-20150901) relying on the articles refered by
WikiProject Biography [1].

For each article, we extracted the first paragraph (text), the infobox
(structured data). Each infobox is encoded as a list of (field name, field
value) pairs. We used Stanford CoreNLP [2] to preprocess the data, i.e. we
broke the text into sentences and tokenized both the text and the field
values. The dataset was randomly split in three subsets train (80%), valid
(10%), test (10%). We strongly recommend using test only for the final
evaluation.

The data is organised in three subdirectories for train, valid and test.
Each directory contains 7 files

SET.id contains the list of wikipedia ids, one article per line.
SET.url contains the url of the wikipedia articles, one article per line.
SET.box contains the infobox data, one article per line.
SET.nb contains the number of sentences per article, one article per line.
SET.sent contains the sentences, one sentence per line.
SET.title contains the title of the wikipedia article, one per line.
SET.contributors contains the url of the wikipedia article history, which list
the authors of the article.

Hence all the file allows to access the information for one article relying
on line numbers. It is necessary to use SET.nb to split the sentences
(SET.sent) per article. The format for encoding the infobox data SET.box
follows the following scheme: each line encode one box, each box is encoded
as a list of tab separated tokens, each token has the following form
fieldname_position:wordtype. We also indicates when a field is empty or
contains no readable tokens with fieldname:<none>. For instance the first
box of the valid set starts with

type_1:pope name_1:michael  name_2:iii      name_3:of
name_4:alexandria title_1:56th    title_2:pope    title_3:of      title_4:alexandria
title_5:&       title_6:patriarch       title_7:of      title_8:the
title_9:see       title_10:of     title_11:st.    title_12:mark   image:<none>

which indicates that the field "type" contains 1 token "pope",
the field "name" contains 4 tokens "michael iii of alexandria",
the field "title" contains 12 tokens "56th pope of alexandria &
patriarch of the see of st. mark", the field "image" is empty.

[1] https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Biography
[2] http://stanfordnlp.github.io/CoreNLP/


== Version Information ==
v1.0 (this version) Initial Release.

== License ==
License information is provided in License.txt
