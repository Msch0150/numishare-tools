# numishare-tools

## Usage {}

Example:

nuds.descMeta.typeDesc.authority.persname[xlink:role="portrait" xlink:href="{}"]

Namespace: nm
Data: augustus

Result:
```
<nuds ...>	
  <descMeta>
		<typeDesc>
			<objectType xlink:type="simple" xlink:href="http://nomisma.org/id/coin"/>
			<authority>
				<persname xlink:role="portrait" xlink:href="http://nomisma.org/id/augustus">augustus</persname>
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
