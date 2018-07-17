# batcode-accounting
	
## Метод GetOrders
+ Параметры
  + status - строка, например "1"
+ Возвращаемое значение
  + Список заданий в XML формате, отобранные по статусу, если статус - пустая строка, то вернет все задания
	
## Метод GetOrder
+ Параметры
  + id - строка, например "8F6"
+ Возвращаемое значение
  + Задание в XML формате, найденное по id
	
## Метод PutOrder
+ Параметры
  + XMLDoc - отсканированные задания в xml формате, например

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<tasklist>
	<task>
		<id>8F6</id>
		<product_list>
			<product>
				<index>0</index>
				<barcode>testbarcode0</barcode>
				<partnint>APAN-ABFKSK</partnint>
				<lotn>0785</lotn>
				<lotd>062020</lotd>
				<qty>8</qty>
			</product>
			<product>
				<index>1</index>
				<barcode>testbarcode1</barcode>
				<partnint>APAN-ABFKTG</partnint>
				<lotn>0789</lotn>
				<lotd>062020</lotd>
				<qty>8</qty>
			</product>
		</product_list>
	</task>
	<task>
		<id>90E</id>
		<product_list>
			<product>
				<index>0</index>
				<barcode>testbarcode2</barcode>
				<partnint>APAN-ABFKSK</partnint>
				<lotn>0785</lotn>
				<lotd>062020</lotd>
				<qty>8</qty>
			</product>
			<product>
				<index>1</index>
				<barcode>testbarcode3</barcode>
				<partnint>APAN-ABFKTG</partnint>
				<lotn>0789</lotn>
				<lotd>062020</lotd>
				<qty>8</qty>
			</product>
		</product_list>
	</task>
</tasklist>
```
+ Возвращаемое значение
  + Ответ в XML формате

## Метод ChangeOrder

+ Параметры
  + XMLDoc - реквизиты изменяемого задания в XML формате, например

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<tasklist>
	<task>
		<id>8F6</id>
		<field>
			<field-name>status</field-name>
			<field-type>text</field-type>
			<field-value>1</field-value>
		</field>	
	</task>
</tasklist>
```

+ Возвращаемое значение
  + Ответ в XML формате, как в методе PutOrder