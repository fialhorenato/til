# Transform multiple lines into a single one

You can use this line to bring multiple lines into line

´´´sql
select 
   {GROUP_COLUMN},
   rtrim (xmlagg (xmlelement (e, {LINE} || '{SEPARATOR}')).extract ('//text()'), '{SEPARATOR}') {COLUMN_NAME}
from 
   {TABLE}
group by 
   {GROUP_COLUMN};
´´´

### Example

For a example, you have a TB_AUTHOR_BOOK, with a ID_AUTHOR and ID_BOOK, n..n and want to return in a single line all the authors

´´´sql
select 
   ID_BOOK,
   rtrim (xmlagg (xmlelement (e, ID_AUTHOR || '{SEPARATOR}')).extract ('//text()'), ';') authors
from 
   TB_AUTHOR_BOOK
group by 
   ID_BOOKS;
´´´