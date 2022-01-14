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
```

## Definition for FMRD
Recommended cite:

FMRD I 7128,9

So, no tomb value as the 7xxx points to the 7th tomb, here Schwaben.

## Usage with direct values


If "|" is used, then the given value should be used. The lookup should not take place:

Values in field: "myRPC I, 522|rpc:522;ocre:ric.1(2).aug.154;ocre:ric.1(2).aug.155"

```
<refDesc>
	<reference></reference>
	<reference xlink:href="https://rpc.ashmus.ox.ac.uk/coins/1/522">myRPC I, 522</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.154">RIC I (second edition) Augustus 154</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.155">RIC I (second edition) Augustus 155</reference>
</refDesc>
```


(Not is use)
```
nuds.descMeta.refDesc.reference[xlink:href="{@}"]
```
Values in field: "@RPC I,522":

```
<refDesc>
	<reference>RPC I, 522</reference>
</refDesc>
```
(Not is use)
Values in field: "@RPC I,522;ocre:ric.1(2).aug.154;ocre:ric.1(2).aug.155":

```
<refDesc>
	<reference>RPC I, 522</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.154">RIC I (second edition) Augustus 154</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.155">RIC I (second edition) Augustus 155</reference>
</refDesc>
```
(Not is use)
Values in field: "@rpc:522;ocre:ric.1(2).aug.154;ocre:ric.1(2).aug.155":

```
<refDesc>
	<reference></reference>
	<reference xlink:href="https://rpc.ashmus.ox.ac.uk/coins/1/522">https://rpc.ashmus.ox.ac.uk/coins/1/522</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.154">RIC I (second edition) Augustus 154</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.155">RIC I (second edition) Augustus 155</reference>
</refDesc>
```
(Not is use)
Values in field: "@RPC I, 522|rpc:522;ocre:ric.1(2).aug.154;ocre:ric.1(2).aug.155":

```
<refDesc>
	<reference></reference>
	<reference xlink:href="https://rpc.ashmus.ox.ac.uk/coins/1/522">RPC I, 522</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.154">RIC I (second edition) Augustus 154</reference>
	<reference xlink:href="http://numismatics.org/ocre/id/ric.1(2).aug.155">RIC I (second edition) Augustus 155</reference>
</refDesc>
```
