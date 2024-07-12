# automation-farmindo

Automation Farmindo digunakan untuk pengecekan hasil Proses PO berdasarkan hasil database secara otomatis.

Informasi Penting
Untuk Proses Assert selalu ada pada bagian Test pada masing-masing Endpoint.
Untuk Class dan Function yang penting ada di bagian Script pada Folder Collection Farmindo Automation Full Cycle.

API Documentation

Login QA

Endpoint ini digunakan untuk melakukan login ke testingqa system.
Response: auth token.

Get Latest Filename

Endpoint ini digunakan untuk mengambil filename terakir pada farmindo system. Data di ambil dari schema farmindo_po dan table pre_incoming.
Response: latest filename.

Get PO PreIncoming

Endpoint ini digunakan untuk mengambil pre incoming data pada farmindo system. Data di ambil dari schema farmindo_po dan table pre_incoming.
Param: fileName yang sebelumnya di set pada API Get Latest Filename.
Response: detail pre incoming data.

Get PO Incoming

Endpoint ini digunakan untuk mengambil po incoming data pada farmindo system. Data di ambil dari schema farmindo_po dan table po_incoming.
Param: preIncomingId yang sebelumnya di set pada API Get PO Pre Incoming.
Response: detail po incoming data.

Get PO Incoming By Seller

Endpoint ini digunakan untuk mengambil po incoming by seller data pada farmindo system. Data di ambil dari schema principal bersangkutan dan table po_incoming.
Param: poNumber dan sellerName yang sebelumnya di set pada API Get PO Incoming
Response: detail po incoming by seller data.

Get Customer Store Mapping

Endpoint ini digunakan untuk mengambil customer store mapping data pada farmindo system. Data di ambil dari schema farmindo dan table customer_store_mapping.
Param: storeMappingId yang sebelumnya di set pada API Get PO Incoming By Seller.
Response: detail customer store mapping data.

Get PO Incoming Detail by Seller

Endpoint ini digunakan untuk mengambil po incoming detail by seller data pada farmindo system. Data di ambil dari schema principal bersangkutan dan table po_incoming_detail.
Param: sellerName yang sebelumnya di set Pada API Get PO Incoming dan poIncomingId yang sebelumnya di set pada API Get PO Incoming By Seller.
Response: detail po incoming detail by seller data.

Get Product Customer

Endpoint ini digunakan untuk mengambil product customer data secara spesifik pada farmindo system. Data di ambil dari schema farmindo dan table product_customer.
Param: productId dan productCode yang sebelumnya di set pada API Get PO Incoming Detail By Seller.
Response: detail product customer data.

Get Product Mapping

Endpoint ini digunakan untuk mengambil product mapping data secara spesifik pada farmindo system. Data di ambil dari schema principal bersangkutan dan table product_mapping.
Param: productMappingId yang sebelumnya di set pada API Get PO Incoming Detail by Seller, sellerName yang sebelumnya di set pada API Get PO Incoming.
Resposne: detail product mapping data.

Get Product Principal

Endpoint ini digunakan untuk mengambil product principal data secara spesifik pada farmindo system. Data di ambil dari schema principal bersangkutan dan table product_principal.
Param: productPrincipalId dan productPrincipalCode yang sebelumnya di set pada API get PO Incoming Detail by Seller, sellerName yang sebelumnya di set pada API Get PO Incoming.
Resposne: detail product principal data.

Get PO Outgoing

Endpoint ini digunakan untuk mengambil po outgoing data pada farmindo system. Data di ambil dari schema farmindo_po dan table po_outgoing.
Param: poNumber yang sebelumnya di set pada API Get PO Incoming
Resposne: detail po outgoing data.

Automation Process Documentation

Login QA

Get Latest Filename

Get PO PreIncoming

Get PO Incoming

Get PO Incoming By Seller

Get Customer Store Mapping

Get PO Incoming Detail By Seller (isCollectInfo False)

Get Product Customer

Get Product Mapping

Get Product Principal (isCollectInfo True)

Get PO incoming Detail By Seller (Verify Price Value by Calculation).
Jika detail lebih dari 1 maka akan kembali ke point 7.
Jika sudah tidak ada detail lagi maka lanjut ke point 8 - 10 tetapi hanya mengembalikan pesan "Pengecekan Detail Selesai",
lalu akan lanjut ke step berikutnya.

Get PO Outgoing.
Jika PO lebih dari 1 maka akan kembali ke point 4.


Run menggunakan Newman

Harus install Newman di link berikut https://learning.postman.com/docs/collections/using-newman-cli/installing-running-newman/
Harus install plugin htmlextra di link berikut
https://www.npmjs.com/package/newman-reporter-htmlextra
Contoh Run Newman dengan lokasi collection dan environment variable ada di direktori F lalu buka CMD dan run command line dibawah ini.
newman run "F:\Farmindo Automation Full Cycle.postman_collection.json" -e "F:\Automation Farmindo.postman_environment.json" -r htmlextra
Setelah di jalankan, maka akan terbuat folder yang terisi report htmlextra dan bisa di buka file report berupa html tersebut.

Push to Bitbucket

Setelah ada perubahan di Collection atau Environment
harus di lakukan export lagi
masukan lagi di folder project hasil clone
lalu coba push lagi menggunakan gitbash atau cmd dengan command
git add
git commit -m "Pesan nya"
git push


Credit

Documentation & Script Creator - Daniel Nurrasyid (202103003)

Endpoint Creator - Steven Lim


