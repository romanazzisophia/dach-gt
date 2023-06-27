## Ground truth and full text for selected prints of German libraries

* [Staatsbibliothek zu Berlin](data/DE-1)
* [Bayerische Staatsbibliothek](data/DE-12) / Münchener Digitalisierungszentrum
* [Thüringer Universitäts- und Landesbibliothek](data/DE-27)
* [Universitäts- und Stadtbibliothek Köln](data/DE-38)
* [Universitäts- und Landesbibliothek Düsseldorf](data/DE-61)


### Collection of useful commands

```
# Remove empty lines from ALTO and PAGE XML.
perl -i -ne "tr|\r||d; next if /^\s*$/;print" *.xml

# Remove ALTO files without fulltext.
rm -f $(grep -L 'CONTENT="..*"' *.xml)

# Remove PAGE files without fulltext.
rm $(grep -L '<Unicode>..*</Unicode>' *.xml)
```
