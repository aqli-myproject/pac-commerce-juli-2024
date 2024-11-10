# Case II : Customer Membership
## PacCommerce adalah layanan E-commerce
PacCommerce memiliki tier membership
- Platinum
- Gold
- Silver
Dari masing-masing tier membership memiliki benefitnya masing-masing yang berbeda.

PacCommerce ingin membuat sistem untuk melakukan prediksi user masuk dalam setiap tier membership. PacCommerce membutuhkan data monthly ekspense dan monthly income user untuk melakukan prediksi sebagai acuan. untuk memprediksi membership user, PacCOmmerce menggunakan pendekatan berdasarkan jarak. cara kerjanya adalah akan mengukur/menghitung jarak antara:
- input (expense & income user) dengan
- parameter (expense & income) dari masing-masing tier membership
membership user dipilih dari tier yang memiliki jarak yang paling dekat dengan input
ada banyak metode untuk menghitung berdasarkan jarak, namun kali ini digunakan Euclidean Distance.

## Membership Table 
| **Membership** | **Discount** |                     **Another Benefit**                     |
|:--------------:|:------------:|:-----------------------------------------------------------:|
|    Platinum    |      15%     | Benefit Silver + Gold + Voucher Liburan + Cashback max. 30% |
|      Gold      |      10%     | Benefit Silver + Voucher Ojek Online                        |
|     Silver     |      8%      | Voucher Makanan                                             |


## Requirements Membership Table 
| **Membership** | **Monthly Expense (juta)** | **Monthly Income (juta)** |
|:--------------:|:--------------------------:|:-------------------------:|
|    Platinum    |              8             | 15                        |
|      Gold      |              6             | 10                        |
|     Silver     |              5             | 7                         |

## Problem & Objective
membuat simpel program untuk memprediksi membership user PacCommerce
membuat fitur yang dimana user nanti bisa melakukan:
- show all tier dan membership yang tersedia di PacCommerce
- show ketentuan jumlah monthly expense dan monthly income yang dibutuhkan dari masing-masing membership
- predict user masuk ke dalam membership mana berdasarkan parameter expense dan income
- calculate total belanja akhir berdasarkan tier membership PacCommerce
untuk membuat fitur tersebut kita bisa menggunakan User Data, dimana isinya terdapat:
- User Name
- MOnthly Expense
- Monthly Income
- Membership

## Requirment Fitur yang dibutuhkan
- [x] `show_benefit()` --> show all membership benefit (table 1)
- [x] `show_requirements()` --> show all requirements untuk menjadi membership (table 2)
- [x] `predict_membership(monthly_expense, monthly_income)` --> memprediksi user akan masuk ke dalam membership mana berdasarkan input parameter dan parameter masing - masing membership
- [x] `calculate_price(membership, list_harga_barang)` --> menghitung final price yang harus dibayarkan, terus akan mendapatkan diskon sesuai dengan ketentuan membership

---------------------------------------------------
## Validation Program
Create an instance of Membership for a user
obj_1 = Membership(username="Santoso")

---------------------------------------------------
Display the benefits of each membership tier
obj_1.show_benefit()

---------------------------------------------------
Predict the membership tier for the user based on monthly expense and income
obj_1.predict_membership(monthly_expense=3, monthly_income=20)

---------------------------------------------------
Display the updated membership data
print(obj_1.data)

---------------------------------------------------
