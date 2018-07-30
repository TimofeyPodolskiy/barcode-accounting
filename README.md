# barcode-accounting
	
## Метод GetOrders
+ Параметры
  + status - строка, например "1"
+ Возвращаемое значение
  + Список заданий в XML формате, отобранные по статусу, если статус - пустая строка, то вернет все задания
	
## Метод GetOrder
+ Параметры
  + id - строка, например "8F6"
  + userCn - строка, lotus имя пользователя 
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
				<barcodes>
					<barcode>testbarcode0</barcode>
					<barcode>testbarcode1</barcode>
					<barcode>testbarcode2</barcode>
					<barcode>testbarcode3</barcode>
					<barcode>testbarcode4</barcode>
					<barcode>testbarcode5</barcode>
					<barcode>testbarcode6</barcode>
					<barcode>testbarcode7</barcode>
				</barcodes>
				<partnint>APAN-ABFKSK</partnint>
				<lotn>0785</lotn>
				<lotd>062020</lotd>
				<qty>8</qty>
			</product>
			<product>
				<index>1</index>
				<barcodes>
					<barcode>testbarcode10</barcode>
					<barcode>testbarcode11</barcode>
				</barcodes>
				<partnint>APAN-ABFKTG</partnint>
				<lotn>0789</lotn>
				<lotd>062020</lotd>
				<qty>2</qty>
			</product>
		</product_list>
	</task>
	<task>
		<id>90E</id>
		<product_list>
			<product>
				<index>0</index>
				<barcodes>
					<barcode>testbarcode8</barcode>
				</barcodes>
				<partnint>APAN-ABFKSK</partnint>
				<lotn>0785</lotn>
				<lotd>062020</lotd>
				<qty>1</qty>
			</product>
			<product>
				<index>1</index>
				<barcodes>
					<barcode>testbarcode9</barcode>
				</barcodes>
				<partnint>APAN-ABFKTG</partnint>
				<lotn>0789</lotn>
				<lotd>062020</lotd>
				<qty>1</qty>
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


## Метод LoginUser

+ Параметры
  + usercode - номер пользователя, например 00123422220001

+ Возвращаемое значение
  + Информация о пользователе, или сообщение об ошибке