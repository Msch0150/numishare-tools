# FMRD
Recommended citation:

FMRD I 7128,9

Abteilung I = Bayern

Fundkomplex 7128 => 7xxx = Schwaben

Münze Nr. 9

## Implementation (draft)

Admin UI > Modify settings > Contents, Local Types and Symbol Positions

Local Types + > Attribute Value "fmrdFindComplex", Textual Label "FMRD find complex" (English)

+Label > Textual Label "FMRD Fundkomplex" (German)

Local Types + > Attribute Value "fmrdCoinNumber", Textual Label "FMRD coin number" (English)

+Label > Textual Label "FMRD Münz Nr." (German)


Add in Admin UI > Modify settings > Factes > + : fmrdFindComplex_facet

Here only "fmrdFindComplex_facet" needs to be added because the "fmrdCoinNumber" does not need to be indexed.

That works! Maybe you have to reindex the collection.

Config and translation for facets is stored in config.xml in the exist DB.

===

        

Needs to be done in this way because otherwise the search might not work.
Translation should be done in:


Maybe:
./numishare/ui/xslt/functions.xsl:

...
 <xsl:when test="$label='fmrdFindComplex'">FMRD Fundkomplex</xsl:when>
 <xsl:when test="$label='fmrdCoinNumber'">FMRD Münz Nr.</xsl:when>
...

and in the default "en" at the end to the xsl file.

Does not work!
