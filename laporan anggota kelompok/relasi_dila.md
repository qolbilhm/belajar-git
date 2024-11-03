## contoh 1
Kode : 
```SQL
SELECT order.OrderID, orders.OrderDate, orders.CustID,
    -> customers.CompanyName, customers.ContactName, customers.City,
    -> customers.Phone
    -> FROM order, orders, customers
    -> WHERE (orders.custID  = customers.customerID);
```

![contoh1|590](assets01/contoh1.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `orders.orderID` = orders merupakan nama tabel yang ingin ditampilkan kolomnya yaitu orderID. Jadi kolom orderID pada dalam tabel orders ingin ditampilkan.
- `orders.orderDate` = kolom orderDate pada dalam tabel orders ingin ditampilkan.
- `orders.custID`= kolom custID dalam tabel orders dipilih untuk ditampilkan.
- `customers.companyName` = kolom companyName dalam tabel customers dipilih untuk ditampilkan.
- `customers.contactName` = kolom contactName dalam tabel customers dipilih untuk ditampilkan.
- `customers.city` = kolom city dalam tabel customers dipilih untuk ditampilkan.
- `customers.phone` = kolom phone dalam tabel customers dipilih untuk ditampilkan.
- `FROM orders, customers` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan. orders adalah nama tabel pertama yang dipilih dan customers adalah nama tabel kedua yang dipilih.
- `WHERE` =kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(orders.custID = customers.customersID)` = kondisi dari WHERE yang harus dipenuhi. Jadi, data pada kolom custID dalam tabel orders harus sama dengan data pada kolom customersID dalam tabel customers agar  masing-masing datanya bisa ditampilkan.

HASIL : 
Jadi yang tampil adalah kolom orderID, orderDate dan custID dari tabel orders dan kolom companyName, contactName, city, dan phone dari tabel customers.

## contoh 2
kode : 
```SQL
SELECT o.OrderID, o.OrderDate, o.CustID,
    -> c.CompanyName, c.ContactName, c.City,
    -> c.Phone
    -> FROM orders o, customers c
    -> WHERE o.CustID = c.CustomersID AND c.City = "London";
```

![contoh2|580](assets01/contoh2.png)

penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.orderID` = o merupakan singkatan dari tabel orders. kolom orderID merupakan kolom dari tabel orders yang dipilih untuk ditampilkan.
- `o.orderDate` = kolom orderDate merupakan kolom dari tabel o yaitu orders yang dipilih untuk ditampilkan.
- `o.custID` = kolom custID merupakan kolom dari tabel o yaitu orders yang dipilih untuk ditampikan.
- `c.companyName` = c merupakan singkatan dari tabel curtomers. kolom companyName merupakan kolmo dari tabel customers yang dipilih untuk ditampilkan.
- `c.contactName` = kolom contactName merupakan kolom dari tabel c yaitu customers yang dipilih untuk ditampilkan.
- `c.city` = kolom city merupakan kolom dari tabel c yaitu customers yang dipilih untuk ditampilkan.
- `c.phone` = kolom phone merupakan kolom dari tabel c yaitu customers yang dipilih untuk ditampilkan.
- `FROM orders o, customers c` = untuk memilih dari tabel mana saja yang kolomnya ingin dipilih untuk ditampilkan tapi disingkat jadi o, agar lebih mudah dan cepat. customers adalah nama tabel yang dipilih untuk ditampilkan tapi disingkat menjadi c.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(o.custID = c.customerID` = data pada kolom custID dalam tabel o (orders) harus sama dengan data pada kolom customerID dalam tabel c (customers).
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `c.city = "London"` = kondisi tambahan yang harus dipenuhi juga. Jadi pada kolom city dari tabel c (customers) datanya harus berisi data "London"  agar bisa ditampilkan.

HASIL : 
Jadi hanya barisan data yang kolom city dari tabel customers mempunyai data "London" yang bisa tampil.

## contoh 3
kode : 
```SQL
SELECT o.OrderID, o.OrderDate, c.CompanyName,
    -> c.ContactName, c.Phone, e.LastName, e.Title
    -> FROM orders o, customers c, employees e
    -> WHERE o.CustID = c.CustomerID AND o.EmpID = e.EmpID;
```

![contoh3|590](assets01/contoh3.png)

penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.orderID, o.orderDate` = kolom orderID dan orderDate dari tabel o(order) dipilih untuk ditampilkan.
- `c.companyName, c.contactName, c.phone` = kolom-kolom companyName, contactName dan phone dari tabel c(customers) dipilih untuk ditampilkan.
- `e.LastName, e.Title` = kolom lastName dan titke dari tabel e(employees) dipilih untuk ditampilkan.
- `FROM orders o, customers c, employees e` = untuk memiliih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan. orders disingkat jadi o adalah nama tabel yang dipilih. customers disingkat jadi c adalah nama tabel yang dipilih. employees disingkat jadi e adalah nama tabel yang dipilih untuk ditampilkan.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu data agar bisa ditampilkan.
- `(o.custID = c.customerID)` data pada kolom  custID dalam tabel  (orders) harus sama dengan data pada kolom customerID dalam tabel .(customers.)
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `(o.empID = e.empID)` = data pada kolom empID dalam tabel o(orders) harus sama dengan data pada kolom empID dalam tabel e(employees).

HASIL : 
Yang tampil adalah kolom yang memenuhi semua kondisi dari WHERE.

## Contoh 4
kode : 
```SQL
SELECT o.OrderID, o.OrderDate, c.CompanyName,
    -> c.ContactName, c.Phone, e.LastName, e.Title
    -> FROM orders o, customers c, employees e
    -> WHERE o.CustID = c.CustomerID AND o.EmpID = e.EmpID AND
    -> e. FirstName = "Margaret";
```

![contoh4|580](assets01/contoh4.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `o.orderID, o.orderDate` = kolom orderID dan orderDate dari tabel o(orders) dipilih untuk ditampilkan.
- `c.companyName, c.contactName, c.Phone` = kolom companyName, contactName dan Phone dari tabel c(customers) dipilih untuk ditampilkan.
- `e.LastName, e.Title` = kolom lastName dan Title dari tabel e(employees) dipilih untuk ditampilkan.
- `FROM orders o,customers c, employees e`  = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan. orders atau o adalah nama tabel yang dipilih untuk ditampilkan, customers atau c adalah  nama tabel yang dipilih untuk ditampilkan. employees atau e adalah nama tabel yang dipilih untuk ditampilkan. 
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(o.custID = c.customerID` = data pada kolom custID dalam tabel o(orders) harus sama dengan data pada kolom customerID dalam table c(customers).
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `(e.FirstName = "margaret")` = data pada kolom firstName dalam tabel e(employees) harus berisi data "margaret" agar bisa tampil.

HASIL : 
jadi barisan data yang sudah menenuhi  kondisi WHERE akan tampil terutama kolom firstName dari tabel employees yang isinya "margaret".

## Contoh 5
kode : 
```SQL
SELECT c.CustomerID, c.CompanyName, o.OrderID,
    -> o.OrderDate, od.ProductID, p.ProductName,
    -> od.Quantity AS Qty, od.UnitPrice
    -> FROM customers c, orders o, orderdetails od, products p
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> AND p.ProductID = od.ProductID
    -> ORDER BY c.CustomerID;
```

![contoh5|580](assets01/contoh5.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dari tabel mana kolom tersebut diambil.
- `c.customerID, c.companyName` = kolom customerID dan companyName dari tabel c(customers) dipilih untuk ditampilkan.
- `o.orderID, o.orderDate` = kolom orderID dan orderDate dari tabel o(orders) dipilih untuk ditampilkan.
- `od.ProductID, od.Quantity, od.UnitPrice` = kolom productID, Quantity dan UnitPrice dari table od(orderDetails) dipilih untuk ditampilkan.
- `p.ProductName` = kolom productName merupakan kolom dari tabel p(products) yang dipilih untuk ditampilkan.
- `od.Quantity AS qty` = kolom quantity ditampilkan sebagai nama sementaranya yaitu qty. AS untuk mengubah nama suatu kolom secara sementara.
- `FROM customers c, orders o, orderdetails od, product p` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan, customers atau c adalah nama tabel yang dipilih untuk ditampilkan. orders atau o adalah nama tabel yang dipilih untuk ditampilkan. orderdetails atau od adalah nama tabel yang dipilih untuk ditampilkan. products atau p adalah nama tabel yang dipilih untuk ditampilkan.
- `WHERE`= kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(c.customerID = o.custID)` = data pada kolom customerID dari tabel customers atau c harus sama dengan data pada kolom custID dari tabel orders atau o.
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `(o.orderID =  od.orderID)` = data pada kolom orderID dari tabel orders atau o harus sama dengan data pada kolom orderID dari tabel orderdeatils atau od.
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `(p.productIID = od.productID)` = data pada kolom productID dari tabel products atau p harus sama dengan data pada kolom productID dari tabel orderdeatils atau od.
- `order BY c.customerID` = untuk mengurut data berdasarkan kolom customerID dari tabel customers.

HASIL : 
kolom-kolom data yang tampil adalah data yang telah memenuhi kondisi-kondisi yang ada, dan seluruh isis data tersebut diurut berdasarkan satu kolom yaitu customerID dari tabel customers.


## Contoh 6
kode : 
```SQL
 SELECT c.CustomerID, c.CompanyName, o.OrderID AS OrdID, o.OrderDate, CONCAT(e.LastName, ',', e.FirstName)
    -> AS EmployeeName, od.ProductID AS ProdID,
    -> p.ProductName, od.Quantity AS Qty FROM customers c, orders o, orderdetails od, products p, employees e
    -> WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID AND p.ProductID = od.ProductID
    ->  AND e.EmpID = o.EmpID ORDER BY o.OrderID;
```

![contoh6](assets01/contoh6.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan digabungkan serta dari tabel mana kolom tersebut dipilih.
- `c.customerID, c.companyName` = kolom orderID dan orderDate dari tabel c(customers) dipilih untuk ditampilkan.
- `o.orderID AS ordID, o.orderDate` = kolom orderID dan orderDate dari tabel o(orders) dipilih untuk ditampilkan. sedangkan AS merupakan perintah untuk mengubah nama suatu kolom secara sementara. Dalam hal ini kolom orderID diubah namanya sementara menjadi ordID.
- `CONCAT (e.lastName, ',', e.firstName) AS EmployeeName` =  CONCAT adalah perintah untuk menggabungkan beberapa kolom data menjadi satu kolom data. (e.lastName, ',', e.firstName) merupakan kolom dari tabel e(employees) yang ingin digabung. (',') merupakan separator atau pemisah dari antara kedua kolom yang ingin digabungkan. AS EmployeeName untuk mengubah hasil CONCAT tadi menjadi EmployeeName (namanya) untuk sementara.
- `od.productID AS prodID, od.quantity AS qty` = kolom productID dan quantity dari tabel od(orderdetails) dipilih untukk ditampilkan. kolom productID namanya diubah sementara jadi prodID. kolom quantity namanya diubah sementara jadi qty.
- `p.productName` = kolom dari tabel p(products) dipilih untuk ditampilkan.
- `FROM customers c, orders o, orderdetails od, products p employees e` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan, customers atau c adalah nama tabel yang dipilih untuk ditampilkan. orders atau o adalah nama tabel yang dipilih untuk ditampilkan. orderdetails atau od adalah nama tabel yang dipilih untuk ditampilkan. products atau p adalah nama tabel yang dipilih untuk ditampilkan. employees atau e adalah nama tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu kolom data agar bisa ditampilkan.
- `(c.customerID = o.custID)` = data pada kolom customerID dari tabel customers atau c harus sama dengan data pada kolom custID dari tabel orders atau o.
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `(o.orderID = od.orderID)` = data pada kolom customerID dari tabel c(customers) harus sama dengan data pada kolom orderID dari tabel od(orderdetails).
- `AND` = untuk menyeleksi dua data atau lebih pada perintah WHERE.
- `(e.EmpID = o.EmpID)` = data pada kolom EmpID dari tabel e(Employees) harus sama dengan data pada kolom EmpID dari tabel o(orders).
- `ORDER BY o.orderID` = untuk megurut data berdasarkan kolom orderID dari tabel orders.

HASIL : 
kolom lastName dan firtsName dari tabel e(Employees) digabung dengan CONCAT dan hasil kolomnya namanya diubah sementara jadi EmployeeName.
dar

## Contoh 7
kode : 
```SQL
CREATE VIEW CustOrderEmp
    -> AS
    -> SELECT c.CustomerID, c.CompanyName, c.ContactName,
    -> o.OrderID, o.OrderDate, e.EmpID, e.LastName, e.FirstName
    -> FROM customers c, orders o, employees e
    -> WHERE c.CustomerID = o.CustID AND o.EmpID = e.EmpID;
```

![contoh7|590](assets01/contoh7.png)

Penjelasan : 
- `CREATE VIEW custorderEmp` = merupakan tabel virtual yang dibuat dengan nama custorderEmp.
- `AS SELECT` = untuk memilih kolom-kolom mana saja yang ingin dipilih untuk dimasukkan ke tabel virtual.
- `c.CustomerID, c.CompanyName, c.ContactName` = kolom customersID, CompanyName dan ContactName dari tabel c(customers) dipilih untuk dimasukkan ke dalam tabel virtual.
- `o.orderID, o.orderDate` = kolom orderID dan orderDate dari tabel o(orders) dipilih untuk dimasukkan ke dalam tabel virtual.
- `e.EmpID, eLastName, e.FirstName` = kolom EmpID, LastName, dan FirstName dari tabel e(employees) dipilih untuk dimasukkan ke dalam tabel virtual.
- `FROM  customers c, o orders, employees e` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk dimasukkan. customers, orders, dan employees merupakan nama tabel yang kolomnya dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu data agar bisa dimasukkan ke dalam tabel virtual.
- `(c.CustomerID = O.CustID)` = data pada kolom customerID dari tabel c(customers) harus sama dengan data pada kolom custID dari tabel 0(orders) agar bisa dimasukkan.
- `AND` =untuk menyeleksi dua data atau lebih pada WHERE.
- `(o.EmpID = e.EmpID)` = data pada kolom EmpID dari tabel o(orders) harus sama dengan data pada kolom EmpID dari tabel e(employees) agar bisa di masukkan.

HASIL : 
sebuah tabel virtual telah dibuat dengan nama custorderEmp yang berisi kolom-kolom dari 3 tabel customers, orders, employees dan telah memenuhi semua kondisi.

## Contoh 8
kode : 
```SQL
CREATE VIEW odproducts
    -> AS
    -> SELECT od.OrderID, od.ProductID, p.ProductName,
    -> od.Quantity, od.UnitPrice
    -> FROM orderdetails od, products p
    -> WHERE  p.ProductID = od.ProductID;
```

![contoh8|400](assets01/contoh8.png)

![hasil_query|450](assets01/hasil_8.png)

Penjelasan : 
- `CREATE VIEW odproducts` = untuk membuat tabel virtual dengan nama odproducts.
- `AS SELECT` = untuk memilih kolom-kolom mana saja yang ingin dipilih untuk dimasukkan ke tabel virtual.
- `od.orderID, od.ProductID, od.UnitPrice, od.quantity` = kolom orerID, productID, UnitPrice dan quantity dari tabel od(orderdetails) dipilih untuk dimasukkan.
- `p.productName` = kolom productName dari tabel p(product) dipilih untuk dimasukkan.
- `FROM orderdetails od, product p` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk dimasukkan. orderdetils dan products adalah nama tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu data agar bisa dimasukkan ke dalam tabel virtual.
- `(p.productID = od.productID)` = data pada kolom productID dari tabel p(product) harus sama dengan kolom productID dari tabel od(orderdetails) agar bisa dimasukkan.

HASIL : 
tabel virtual yang bernama odproducts yang terbuat dari kolom dalam 2 tabel : orderdetails dan products.

## Contoh 9
kode : 
```SQL
SELECT c.CustomerID, c.CompanyName, o.OrderID, od.ProductID, ROUND(od.UnitPrice,2), od.Quantity,
    -> od.Discount, ROUND(((1-od.Discount)*od.UnitPrice*od.Quantity),2) AS Jumlah
    -> FROM customer c, orders o, orderdetails od WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> ORDER BY c.CustomerID;
```

![contoh9|600](assets01/contoh9.png)

Penjelasan : 
- `SELECT` =untuk memilih kolom mana saja yang ingin ditampilkan dan dihitung.
- `c.customerID, c.companyName` = kolom customerID dan companyName dari tabel c(customers) dipilih untuk ditampilkan.
- `o.orderID` = kolom orderID dari tabel o(orders) dipilih untuk ditampilkan.
- `od.productID, od.unitPrice, od.quantity, od.Discount` = kolom productID, unitPrice, quantity dan Discount dari tabel od(orderdetails) dipilih untuk ditampilkan dan dibulatkan.
- `ROUND (od.UnitPrice, 2)` = untuk membulatkan bilangan dari kolom UnitPrice sampai jumlah digit tertentu, sesuai dengan pilihan yang dibuat yaitu 2.
- `ROUND (((1-od.Discount) * od.UnitPrice * od.quantity),2) AS jumlah` = untuk membulatkan bilangan dari kolom hasil dari (1 dikurang kolom discount lalu dikali unitPrice dan kali quantity) sampai jumlah digit yaitu 2. AS jumlah untuk mengubah kolom hasil tersebut nama sementaranya jadi jumlah.
- `FROM customers  c, orders o, orderdetails od` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan dan dibulatkan. customers, orders, orderdetails merupakan nama-nama tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu data agar bisa ditampilkan.
- `(c.customerID = o.custID)` = data pada kolom customerID dari tabel c(customers) harus sama dengan data pada kolom custID dari tabel o(orders).
- `AND` = untuk menyeleksi dua data atau lebih pada kondisi WHERE. 
- `(o.orderID = od.orderID)` = data pada kolom orderID dari tabel o(orders) harus sama dengan data pada kolom orderID dari tabel od(orderdetails).
- `ORDER BY c.customerID` = untuk mengurut data berdasarkan kolom customer dari tabel c(customers).

HASIL  : 
akan tampil hasil pembulatan dari kolom-kolom yang telah memenuhi kondisi dari WHERE.


## Contoh 10
kode : 
```SQL
SELECT c.CustomerID, c.CompanyName, ROUND(SUM(1-od.Discount)*od.UnitPrice*od.Quantity),2) AS TotalJumlah
    -> FROM customers c, orders o, orderdetails od WHERE c.CustomerID = o.CustID AND o.OrderID = od.OrderID
    -> GROUP BY c.CustomerID, c.CompanyName ORDER BY c.CustomerID;
```

![contoh10](assets01/contoh10.png)

Penjelasan : 
- `SELECT` = untuk memilih kolom mana saja yang ingin ditampilkan dan dibulatkan.
- `c.customerID, c.companyName` = kolom customerID dan companyName dari tabel c(customers) dipilih untuk ditampilkan.
- `ROUND (SUM((1-od.discount) * od.unitPrice * od.quantity),2) AS Total jumlah` = untuk membulatkan hasil SUM dari ((1 dikurang kolom discount) dikali unitPrice kali quantity) sampai 2 digit. Dan nama kolom hasilnya diubah sementara jadi Total Jumlah.
- `FROM customers c, orders o, orderdetails od` = untuk memilih dari tabel mana saja yang kolomnya dipilih untuk ditampilkan dan dibulatkan. customers, orders, dan orderdetails adalah nama tabel yang dipilih.
- `WHERE` = kondisi yang harus dipenuhi oleh suatu data agar bisa ditampilkan.
- `(c.customerID = o.custID)` = data pada kolom customerID dari tabel c(customers) harus sama dengan data pada kolom custID dari tabel o(orders).
- `AND` = untuk menyeleksi dua data atau lebih pada kondisi WHERE.
- `(o.orderID = od.orderID)` = data pada kolom orderID dari tabel o(orders) harus sama dengan data pada kolom orderID dari tabel od(orderdetails).
- `GROUP BY c.customerID` = untuk mengurut data berdasarkan kolom customerID dari tabel c(customers).

HASIL : 
jadi, kolom yang dikelompokkan adalah customerID dan companyName dan tampilan datanya diurutkan berdasarkan kolom customerID.
