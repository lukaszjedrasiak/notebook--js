The `<table>` element supports these **additional** properties:
- `table.rows` - the collection of `tr`
- `table.caption` - reference to `caption`
- `table.thead` - reference to `thead`
- `table.tfoot` - reference to `tfoot`
- `table.tBodies` - the collection of `tbody`. It can be many of them, but at least one (the browser will put one in the DOM, even if it isn't specified in the source code)

The `<tr>` element provides:
- `tr.cells` - the collection of `td` and `th` inside the row
- `tr.sectionRowIndex` - index of row inside the enclosing `thead` / `tbody` / `tfoot`
- `tr.rowIndex` - index of row inside whole table

The `<td>` and `<th>` elements provide:
- `td.cellIndex` - the index of the cell inside the enclosing `tr`