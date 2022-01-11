# numishare-tools

## Usage {}

Example:

nuds.descMeta.typeDesc.authority.persname[xlink:role="portrait" xlink:href="{@}"]

Namespace: nm
Data: augustus

This get get the preffered label via rdf requst for http://nomisma.org/id/augustus. The preffered label will be set as value and the link will substitute the {@}-field in the attributes list.

Result:
```
<nuds ...>	
  <descMeta>
		<typeDesc>
			<objectType xlink:type="simple" xlink:href="http://nomisma.org/id/coin"/>
			<authority>
				<persname xlink:role="portrait" xlink:href="http://nomisma.org/id/augustus">Augustus</persname>
			</authority>
    </typeDesc>
	</descMeta>        
</nuds>        
```

## Example for two portraits
It should look like:
```
<obverse>
    <persname xlink:type="simple" xlink:role="portrait" xlink:href="http://nomisma.org/id/agrippa">Agrippa</persname>
    <persname xlink:type="simple" xlink:role="portrait" xlink:href="http://nomisma.org/id/augustus">Augustus</persname>
</obverse>
```

## Example for Literature
```
nuds.descMeta.subjectSet.subject[localType="Literature" xlink:href="{}" xlink:type="simple"]
```

first Display name|first link;next display name|next link

Example: K. Kraft, Haltern. In: Bonner Jahrb. 155/156, 105-124|http://wordcat.org/id/123456
Example multiple:
Kraft, Haltern. In: Bonner Jahrb. 155/156, 1955/56, 105-124|http://www.worldcat.org/oclc/632554114;P.-A. Besombes/J.-N. Barrandon, Les dupondii de Nîmes. In: Revue numismatique 157, 2001, 305-328|https://www.persee.fr/doc/numi_0484-8942_2001_num_6_157_2331
It should look like:
```
<subjectSet>
	<subject localType="Literature" xlink:href="http://www.worldcat.org/oclc/632554114" xlink:type="simple">Kraft, Haltern. In: Bonner Jahrb. 155/156, 1955/56, 105-124/subject>
	<subject localType="Literature" xlink:href="https://www.persee.fr/doc/numi_0484-8942_2001_num_6_157_2331" xlink:type="simple">P.-A. Besombes/J.-N. Barrandon, Les dupondii de Nîmes. In: Revue numismatique 157, 2001, 305-328</subject>
</subjectSet>
