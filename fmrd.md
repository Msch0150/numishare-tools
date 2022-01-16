# FMRD
Recommended citation:

FMRD I 7128,9

Abteilung I = Bayern

Fundkomplex 7128 => 7xxx = Schwaben

Münze Nr. 9

## Implementation (draft)

Add in Admin UI > Modify settings > Factes > + : fmrdFindComplex_facet

        
        <subject localType="fmrdFindComplex">IV 3456</subject>
        <subject localType="fmrdCoinNumber">9</subject>
        

Needs to be done in this way because otherwise the search might not work.
Translation should be done in:


Maybe:
./numishare/ui/xslt/functions.xsl:

...
 <xsl:when test="$label='fmrdFindComplex'">FMRD Fundkomplex</xsl:when>
 <xsl:when test="$label='fmrdCoinNumber'">FMRD Münz Nr.</xsl:when>
...

Does not work!
