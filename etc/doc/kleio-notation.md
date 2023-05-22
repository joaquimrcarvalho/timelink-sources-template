# How to transcribe sources with the Kleio notation #

## General notation ##

The Kleio notation uses the concepts of `group`, `element`, `aspect`.

`Groups` represent entities, such as people, objects, institutions, and also acts (like baptisms, marriages, burials), events. 

Groups are similar to database tables that store information about real world entities or events. Groups have a name that denotes the type of entity they describe.

Groups are registered with their name followed with a dollar sign:

        person$
        father$
        mother$
        baptism$
        marriage$

`Elements` register information about groups, such as names of people, dates of acts, places of events. In databases the elements correspond the columns or fields of the database that register information about real world entities. 

Elements are registered with their name, followed by the = sign and the value of element. Sucessive elements are separated by a slash.

        person$name=John Smith/sex=m

In most cases elements appear in a group in a predetermined order, and it is not necessary to name the element explicitly.

        person$John Smith/m

`Aspects` are diferent perspectives on the value of elements. There are three different aspects: `core`, `comment` and `original`. 

Core corresponds to the actual value of the element and must be present; `comment` is a comment on the value and `original` a representation of the original ortography of the value, if it is relevant. Comments are introduced with the # sign and original wording with the % sign.

    person$John Smith#Clear signature%John Smythe

## The source oriented model ##

Timelink uses the general notation above in a specific model that facilitates registration of personal information in historical sources. 

The model is based on a structure source/act/actor-object/attributes-relations

Each source contains one or more acts. Each act contains actors (people) and in some cases objects (e.g. properties).

Each person or object contains information about individual attributes and about relations with other people or objects.


Person/object related information is registred in `ls$` (life-story) and `rel$` (relation) groups.

        kleio%
            source$
                act$
                    person$
                        ls$ (atributes of the person)
                        rel$ (relations of the person)

       

When transcriptions are processed by Timelink, information is replicated along the hierarchy, avoiding unecessary repetitions. For instance, the attributes and relations of people are registered with the date of the act in which they were recorded (this can be overriden when necessary with a specific date). 

People in acts are registered using group names that denote their function in the act: child$, father$, mother$

Also acts are registered using group names that refer to the type of act: bap$ (for baptism) or mar$ (for marriage).

## Transcription structure ##

Timelink transcription files start with the kleio$ header:

        kleio$gacto2.str

Where `gacto2.str` designates the model used for the source transcription, and should not be changed in the current version.

After the `kleio$` header comes the `source$` declaration that identifies the history sources that originated the information in the file:

        source$bap1681/1681/parish registers - baptisms/Ms 15644

The elements in order are: 
* an id that identifies the source and should be unique: bap1681
* the year, or a base year for the source: 1681
* the type of the sources: parish registers - baptisms
* the reference to the source in the archive or library: Ms 15644

Of these elements the `id` is the most relevant, since it serves to identify uniquely this source in the database. When sources are imported into the database they will replace previous versions with the same id. So it is importat to guarentee that each source has a unique id.

The year serves mainly the purpose of ordering sources chronologically. The important dates in the transcriptions will be the dates associated with the acts inside the source, or specific dates associated with attributes of people. 

Historical sources are handled as collections of `acts`. 

An act is something that happened at a certain place in a certain moment of time. For instance: baptisms, marriages, burialsm, deed, purchases, inquiries of witnesses in judicial processes, meeting minutes. These are all examples of `acts`. 

Acts are registered by groups that denote the type of act, normally abreviated: bap$, mar$, bur$.

        kleio$gacto2.str
            source$bap1681/1681/parish registers - baptisms/Ms 15644  
                bap$b1681.1/4/5/1681/fol=23/loc=parish church


Acts have their own attributes, such as the date, the place and the folio of the manuscript where they appear.

The core information of acts relates to the people involved or the objects/entities referred to. People are registered in acts with the role or function they played in the event that the act records. For instance: father, mother, godfather, godmother, seller, buyer, bride, groom, etc... 

....