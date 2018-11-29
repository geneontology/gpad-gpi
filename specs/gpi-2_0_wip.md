## GPI Syntax


### GPI Document Structure

    GPI_Doc ::= GPI_Header Entity*

### GPI Header

A header consists of an obligatory format version declaration followed
by zero or more lines starting with an exclamation point:

    GPI_Header ::= '!gpi-version: 2.0' nl
                   Header_Line*

Each metadata line starts with an exclamation mark '!'. One mark
indicates a structured tag-value pair, two marks indicates free text.

    GPI_Header_Line ::=
       '!' Property_Symbol ':' Space* Value nl |
       '!!' (Char - nl)* nl
      
#### Proposed additional required header lines:
    !gpi_date:YYYY-MM-DD
    !so_version:<PURL>
    !gpi_version:<PURL>
    
#### Other possible entries in the header (these have mostly been taken from what currently exists, but it would be good to get uniformity here)
    !Project_name:
    !URL:
    !Source_database_version:
    !Funding:
    !Contact_email:
    
    Some groups also include the actual file specs with examples (see MGI and Xenbase).  Do we need this?

### GP Entities

A GP entity is any biological entity that can be annotated using GPAD

![image](gpi-uml.png)

Each entity is written on a separate line of tab separated values:

    Entity ::= Col_1 tab Col_2 tab ... Col_9 nl

Each of these columns has its own syntax, as specified below:

1. `DB ::= Prefix`
2. `DB_Object_ID ::= Local_ID`
3. `DB_Object_Symbol ::= xxxx`
4. `DB_Object_Name ::= xxxx`
5. `DB_Object_Synonyms ::= [Label] ('|' Label)*`
6. `DB_Object_Type ::= Type_Symbol`
7. `DB_Object_Taxon ::= Taxon_ID`
8. `Parent_ObjectID ::= [ID??] ('|' ID)*`
9. `DB_Xrefs ::= [ID??] ('|' ID)*`
10. `Properties ::= [Property_Value] (',' Property_Value)*`

The ID for the entity is formed as follows:

    ID = CONCAT( Namespace ':' Local_ID)

*TODO* describe semantics of other columns


### GPI Validation

 * TODO

### GPI Semantics

 * TODO
