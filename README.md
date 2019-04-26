#IUGW2015


Invenio User Group Workshop 2015 - Album/Images Hands-On

Albums/Images in CDS
====================
In CDS, photo records are using MARC in a slighlty different way than other records. Moreover, we are planning to move to a different architecture, where the images are first class citizen, which means each image is a record. For more on splitting, check the  [IUGW2015_split](https://github.com/ludmilamarian/IUGW2015/blob/master/IUGW2015_split.ipynb) IPython notebook.

Let's assume we already have albums and images, as it is the case with the [CERN Photo Archive collection](http://cds/collection/PhotoLab%20Archives). How do we translate them to JSON for CDSLabs?

Record examples:

```
CDS_ALBUM = """
<record>
  <controlfield tag="001">2054964</controlfield>
  <controlfield tag="003">SzGeCERN</controlfield>
  <controlfield tag="005">20150928110024.0</controlfield>
  <datafield tag="963" ind1=" " ind2=" ">
    <subfield code="a">PUBLIC</subfield>
  </datafield>
  <datafield tag="960" ind1=" " ind2=" ">
    <subfield code="a">116</subfield>
  </datafield>
  <datafield tag="961" ind1=" " ind2=" ">
    <subfield code="c">20050915</subfield>
    <subfield code="h">1520</subfield>
    <subfield code="l">MMD01</subfield>
    <subfield code="x">20040702</subfield>
  </datafield>
  <datafield tag="970" ind1=" " ind2=" ">
    <subfield code="a">000030391MMD</subfield>
  </datafield>
  <datafield tag="980" ind1=" " ind2=" ">
    <subfield code="a">PHOTOARC</subfield>
  </datafield>
  <datafield tag="999" ind1=" " ind2=" ">
    <subfield code="a">ALBUM</subfield>
  </datafield>
  <datafield tag="245" ind1=" " ind2=" ">
    <subfield code="a">Assembly tool for BEBC expansion system</subfield>
  </datafield>
  <datafield tag="260" ind1=" " ind2=" ">
    <subfield code="c">1970</subfield>
  </datafield>
  <datafield tag="541" ind1=" " ind2=" ">
    <subfield code="e">Rubrique: Date Planche:9 70 De:479 A:502</subfield>
  </datafield>
  <datafield tag="595" ind1=" " ind2=" ">
    <subfield code="9">11142014-37_191-8-70_300-10-70-6cmx6cm</subfield>
  </datafield>
  <datafield tag="650" ind1="1" ind2="7">
    <subfield code="2">SzGeCERN</subfield>
    <subfield code="a">Industry and Technology</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782445</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782446</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782447</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="n">Cover</subfield>
    <subfield code="r">1782448</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782449</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782450</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782451</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782452</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782453</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782454</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782455</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782456</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782457</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782458</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782459</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782460</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782461</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782462</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782463</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782464</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782465</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782466</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782467</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
    <subfield code="r">1782468</subfield>
  </datafield>
  <datafield tag="596" ind1=" " ind2=" ">
    <subfield code="a">Updated 774 values on run 1443157298</subfield>
  </datafield>
  <datafield tag="269" ind1=" " ind2=" ">
    <subfield code="c">Sep 1970</subfield>
  </datafield>
  <datafield tag="924" ind1=" " ind2=" ">
    <subfield code="t">40</subfield>
  </datafield>
  <datafield tag="500" ind1=" " ind2=" ">
    <subfield code="a">Album with images scanned from original photo negatives</subfield>
  </datafield>
  <datafield tag="340" ind1=" " ind2=" ">
    <subfield code="a">FILM</subfield>
  </datafield>
  <datafield tag="340" ind1=" " ind2=" ">
    <subfield code="a">Neg NB 6 x 6</subfield>
  </datafield>
</record>
"""

CDS_IMAGE = """
<record>
  <controlfield tag="001">1782445</controlfield>
  <controlfield tag="005">20150925091440.0</controlfield>
  <datafield tag="037" ind1=" " ind2=" ">
    <subfield code="a">CERN-PHOTO-7009479</subfield>
  </datafield>
  <datafield tag="110" ind1=" " ind2=" ">
    <subfield code="a">CERN PhotoLab</subfield>
  </datafield>
  <datafield tag="245" ind1=" " ind2=" ">
    <subfield code="a">No caption</subfield>
  </datafield>
  <datafield tag="260" ind1=" " ind2=" ">
    <subfield code="c">1970</subfield>
  </datafield>
  <datafield tag="269" ind1=" " ind2=" ">
    <subfield code="a">Geneva</subfield>
    <subfield code="b">CERN</subfield>
    <subfield code="c">1970-9</subfield>
  </datafield>
  <datafield tag="300" ind1=" " ind2=" ">
    <subfield code="a">Photographic negative</subfield>
    <subfield code="c">6cmx6cm</subfield>
  </datafield>
  <datafield tag="500" ind1=" " ind2=" ">
    <subfield code="a">Image scanned from original photo negative on 14 Nov 2014</subfield>
    <subfield code="3">Box 37_191-8-70_300-10-70</subfield>
  </datafield>
  <datafield tag="541" ind1=" " ind2=" ">
    <subfield code="e">479-9-1970</subfield>
  </datafield>
  <datafield tag="595" ind1=" " ind2=" ">
    <subfield code="a">Archive Collection</subfield>
    <subfield code="s">Scanned by Contentra Technologies</subfield>
    <subfield code="9">11142014-37_191-8-70_300-10-70-6cmx6cm</subfield>
  </datafield>
  <datafield tag="596" ind1=" " ind2=" ">
    <subfield code="a">Updated 774 value on run 1443157342</subfield>
  </datafield>
  <datafield tag="690" ind1="C" ind2=" ">
    <subfield code="a">PHOTO</subfield>
  </datafield>
  <datafield tag="774" ind1=" " ind2=" ">
    <subfield code="a">ALBUM</subfield>
    <subfield code="r">2054964</subfield>
  </datafield>
  <datafield tag="856" ind1="4" ind2=" ">
    <subfield code="s">1770303</subfield>
    <subfield code="u">http://cds.cern.ch/record/1782445/files/70-9-479.jpg</subfield>
    <subfield code="y">Image 70-9-479</subfield>
  </datafield>
  <datafield tag="856" ind1="4" ind2=" ">
    <subfield code="s">143713</subfield>
    <subfield code="u">http://cds.cern.ch/record/1782445/files/70-9-479.jpg?subformat=icon-640</subfield>
    <subfield code="x">icon-640</subfield>
  </datafield>
  <datafield tag="856" ind1="4" ind2=" ">
    <subfield code="s">411079</subfield>
    <subfield code="u">http://cds.cern.ch/record/1782445/files/70-9-479.jpg?subformat=icon-1440</subfield>
    <subfield code="x">icon-1440</subfield>
  </datafield>
  <datafield tag="856" ind1="4" ind2=" ">
    <subfield code="s">74003</subfield>
    <subfield code="u">http://cds.cern.ch/record/1782445/files/70-9-479.jpg?subformat=icon-180</subfield>
    <subfield code="x">icon-180</subfield>
  </datafield>
  <datafield tag="916" ind1=" " ind2=" ">
    <subfield code="s">n</subfield>
    <subfield code="w">201446</subfield>
  </datafield>
  <datafield tag="960" ind1=" " ind2=" ">
    <subfield code="a">86</subfield>
  </datafield>
  <datafield tag="963" ind1=" " ind2=" ">
    <subfield code="a">Public</subfield>
    <subfield code="b">notvisible</subfield>
  </datafield>
  <datafield tag="980" ind1=" " ind2=" ">
    <subfield code="a">PHOTOARCIMAGES</subfield>
  </datafield>
  <datafield tag="999" ind1=" " ind2=" ">
    <subfield code="a">IMAGE</subfield>
  </datafield>
</record>
"""
```

They both have the `774` MARC tag, but each record is using it slightly different
```
<datafield tag="774" ind1=" " ind2=" ">
  <subfield code="a">ALBUM</subfield>
  <subfield code="r">2054964</subfield>
</datafield>
```
```
<datafield tag="774" ind1=" " ind2=" ">
  <subfield code="a">IMAGE</subfield>
  <subfield code="r">1782467</subfield>
</datafield>
<datafield tag="774" ind1=" " ind2=" ">
  <subfield code="a">IMAGE</subfield>
  <subfield code="r">1782468</subfield>
</datafield>
```

Our solution is different translation models:
* for albums: [album fields](https://github.com/CERNDocumentServer/cds/blob/cdslabs/cds/base/dojson/marc21/fields/album.py) and [album translation](https://github.com/CERNDocumentServer/cds/blob/cdslabs/cds/base/dojson/marc21/translations/album.py)
* for images: [image fields](https://github.com/CERNDocumentServer/cds/blob/cdslabs/cds/base/dojson/marc21/fields/image.py) and [image translation] (https://github.com/CERNDocumentServer/cds/blob/cdslabs/cds/base/dojson/marc21/translations/image.py)

```
$inveniomanage shell
```

```
>>> from dojson.contrib.marc21.utils import create_record
>>> from cds.base.dojson.marc21.translations.album import (
        translation as marc21
)

>>> blob = create_record(CDS_ALBUM)
>>> data = marc21.do(blob)

{'base': ['116'],
 'cat': [{'creation_date': '20040702',
   'hour': '1520',
   'library': 'MMD01',
   'modification_date': '20050915'}],
 'collections': [{'primary': 'PHOTOARC'}],
 'control_number': '2054964',
 'control_number_identifier': 'SzGeCERN',
 'date_and_time_of_latest_transaction': '20150928110024.0',
 'general_note': [{'general_note': 'Album with images scanned from original photo negatives'}],
 'images': [{'$ref': 'http://cds.cern.ch/record/1782445',
   'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782446', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782447', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782448',
   'record_type': 'IMAGE',
   'relation': 'Cover'},
  {'$ref': 'http://cds.cern.ch/record/1782449', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782450', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782451', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782452', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782453', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782454', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782455', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782456', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782457', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782458', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782459', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782460', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782461', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782462', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782463', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782464', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782465', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782466', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782467', 'record_type': 'IMAGE'},
  {'$ref': 'http://cds.cern.ch/record/1782468', 'record_type': 'IMAGE'}],
 'immediate_source_of_acquisition_note': [{'accession_number': 'Rubrique: Date Planche:9 70 De:479 A:502'}],
 'imprint': [{'complete_date': 'Sep 1970'}],
 'internal_note': [{'additional_note': '11142014-37_191-8-70_300-10-70-6cmx6cm'}],
 'owner': {'owner': 'PUBLIC'},
 'photolab': [{'photolab_2': '40'}],
 'physical_medium': [{'material_base_and_configuration': ['FILM']},
  {'material_base_and_configuration': ['Neg NB 6 x 6']}],
 'publication_distribution_imprint': [{'date_of_publication_distribution': ['1970']}],
 'record_type': [{'record_type': 'ALBUM'}],
 'slac_note': [{'slac_note': 'Updated 774 values on run 1443157298'}],
 'subject_added_entry_topical_term': [{'level_of_subject': 'Primary',
   'source_of_heading_or_term': 'SzGeCERN',
   'thesaurus': 'Source specified in subfield $2',
   'topical_term_or_geographic_name_entry_element': 'Industry and Technology'}],
 'sysno': {'sysno': '000030391MMD'},
 'title_statement': {'title': 'Assembly tool for BEBC expansion system'}}

```


```
>>> marc21.rules
[..]
('^500..',
  ('general_note',
   <function dojson.contrib.marc21.fields.bd5xx.general_note>,
   re.compile(r'^500..'))),
('^595__',
  ('internal_note',
   <function cds.base.dojson.marc21.fields.default.bd5xx.internal_note>,
   re.compile(r'^595__'))),
('^774[10_][8_]',
  ('images',
   <function cds.base.dojson.marc21.fields.album.images>,
   re.compile(r'^774[10_][8_]'))),
```
