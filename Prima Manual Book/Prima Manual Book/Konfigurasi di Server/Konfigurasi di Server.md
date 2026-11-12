# Konfigurasi di Server

Sebelum melakukan transaksi atau proses lainnya, user perlu melakukan konfigurasi yang diset di level **client** dan **tenant**. Jika konfigurasi belum dilakukan, error dapat terjadi saat transaksi diproses.
## Konfigurasi di Sistem

Konfigurasi berikut dilakukan pada tenant **PT Sebastian Citra Indonesia** dan **PT Primajaya Pantes Garments**. Seluruh konfigurasi dilakukan melalui menu **System Configurator** dengan **Configuration Level** yang diset ke **Client**.

| Name                                                | Configured Value                                                                                                                  | Configuration Level |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| SIS_VARIAN_ALLOW_UPDATE_BOM                         | Y                                                                                                                                 | Client              |
| SIS_VARIAN_ALLOW_UPDATE_PURCHASING                  | Y                                                                                                                                 | Client              |
| SIS_VARIAN_ALLOW_UPDATE_REPLENISH                   | Y                                                                                                                                 | Client              |
| SIS_VARIAN_ALLOW_UPDATE_REPLENISHRDO                | Y                                                                                                                                 | Client              |
| SIS_VARIAN_ALLOW_UPDATE_ROUTING                     | Y                                                                                                                                 | Client              |
| SIS_VARIAN_ALLOW_UPDATE_UOMCONVERSION               | Y                                                                                                                                 | Client              |
| SIS_RDO_Cancel_Delivery_DocType_ID                  | C_DocType_ID                                                                                                                      | Client              |
| SIS_INVENTORY_CHARGE5_URL                           | https://36.94.102.63:5599                                                                                                         | Client              |
| SIS_ALLOW_PO_QTY_MORE_THAN_REQUISITION_QTY          | **Y**: mengizinkan Qty PO lebih dari Qty Requisition. **N**: Qty PO tidak boleh melebihi Qty Requisition                          | Client              |
| SIS_ASSET_DISPOSAL_SO_BP_ID                         | C_BPartner_ID                                                                                                                     | Client              |
| SIS_ASSET_DISPOSAL_SO_PL_ID                         | M_PriceList_ID                                                                                                                    | Client              |
| SIS_ASSET_DISPOSAL_SO_WH_ID                         | M_Warehouse_ID                                                                                                                    | Client              |
| SIS_ActivateAccessDocBasedOnDocTypeAccess           | Y                                                                                                                                 | Client              |
| SIS_ActivateAccessDocBasedOnWarehouseAccess         | Y                                                                                                                                 | Client              |
| SIS_BANKTRANSFER_BP_ID                              | C_BPartner_ID                                                                                                                     | Client              |
| SIS_BANKTRANSFER_CHARGE_ID                          | C_Charge_ID                                                                                                                       | Client              |
| SIS_BANK_PETTY_CASH_ID                              | C_Bank_ID                                                                                                                         | Client              |
| SIS_BASEURL_SERVICE_INVENTORY                       | http://localhost:8019                                                                                                             | Client              |
| SIS_BPGROUPWH_DEFAULT_ID                            | C_BP_Group_ID                                                                                                                     | Client              |
| SIS_BS_CHARGE_ID                                    | C_Charge_ID                                                                                                                       | Client              |
| SIS_CHARGE_ASSET_ADDITION_ID                        | C_Charge_ID                                                                                                                       | Client              |
| SIS_CHARGE_ASSET_TRANSFER_ID                        | C_Charge_ID                                                                                                                       | Client              |
| SIS_CHARGE_POLO_PERCENT                             | 50                                                                                                                                | Client              |
| SIS_Charge_Bank_Transfer                            | C_Charge_ID                                                                                                                       | Client              |
| SIS_DISABLE_CHECK_INVENTORY_MOVE_WHILE_COMPLETE_POP | Menentukan apakah saat complete POP sistem melakukan pengecekan Inventory Move yang masih _outstanding_. Tentukan value Y atau N. | Client              |
| SIS_DOCTYPE_MATCHEDINV_ID                           | C_DocType_ID                                                                                                                      | Client              |
| SIS_EXPIRED_DEFAULT_MINUTES                         | 480                                                                                                                               | Client              |
| SIS_FLEET_BT_BANKACCOUNT_ID                         | C_BankAccount_ID                                                                                                                  | Client              |
| SIS_FLEET_BT_DOCTYPE_ID                             | C_DocType_ID                                                                                                                      | Client              |
| SIS_FLEET_CHARGE_BBM_ID                             | C_Charge_ID                                                                                                                       | Client              |
| SIS_FLEET_CHARGE_PARKIR_ID                          | C_Charge_ID                                                                                                                       | Client              |
| SIS_FLEET_CHARGE_TOL_ID                             | C_Charge_ID                                                                                                                       | Client              |
| SIS_FLEET_CURRENCY_ID                               | C_Currency_ID                                                                                                                     | Client              |
| SIS_FLEET_DEFAULT_DOC_TYPE_ID                       | C_DocType_ID                                                                                                                      | Client              |
| SIS_FLEET_PAYMENT_TERM_ID                           | C_PaymentTerm_ID                                                                                                                  | Client              |
| SIS_FLEET_PRICE_LIST_ID                             | M_PriceList_ID                                                                                                                    | Client              |
| SIS_FLEET_TAX_ID                                    | C_Tax_ID                                                                                                                          | Client              |
| SIS_FLEET_USER_ID                                   | AD_User_ID                                                                                                                        | Client              |
| SIS_INTERNALUSE_MOVEMENT_DOCTYPE_ID                 | C_DocType_ID Inventory Decrease/Increase                                                                                          | Client              |
| SIS_INVENTORY_EXT_URL                               | http://36.95.119.12:5558                                                                                                          | Client              |
| SIS_MATCHING_PARTIAL_SEQUENCE_ID                    | C_DocType_ID                                                                                                                      | Client              |
| SIS_MATCHING_SEQUENCE_ID                            | C_DocType_ID                                                                                                                      | Client              |
| SIS_PL_PURCHASE_ID                                  | M_PriceList_ID                                                                                                                    | Client              |
| SIS_PL_PURCHASE_SCHEMA_ID                           | M_PriceList_ID                                                                                                                    | Client              |
| SIS_PL_SALES_ID                                     | M_PriceList_ID                                                                                                                    | Client              |
| SIS_PL_SALES_SCHEMA_ID                              | M_PriceList_ID                                                                                                                    | Client              |
| SIS_RDO_LOCATOR_INTRANSIT_ID                        | M_Locator_ID                                                                                                                      | Client              |
| SIS_SYSTEM_01                                       | N                                                                                                                                 | Client              |
| SIS_StandardPL_ID                                   | M_PriceList_ID                                                                                                                    | Client              |
| SIS_TAX_EXEMPT_ID                                   | C_Tax_ID                                                                                                                          | Client              |
| SIS_USING_DOCTYPE_MANUAL_ASI                        | Y                                                                                                                                 | Client              |
| SIS_WAITING_QUEUE_DOCNO_SEC                         | 5                                                                                                                                 | Client              |


## Scheduler

**Scheduler** menjalankan proses atau aktivitas tertentu secara otomatis sesuai jadwal yang dikonfigurasi, sehingga user tidak perlu menjalankannya secara manual setiap kali dibutuhkan. Scheduler yang perlu dikonfigurasi:

| Name Scheduler                        | Process                               |
| ------------------------------------- | ------------------------------------- |
| SIS Auto Create Adjustment MR SC      | SIS Auto Create Adjustment MR SC      |
| SIS Auto Generate PLV                 | SIS Auto Generate PLV                 |
| SIS Auto Reposting Matched Invoice    | SIS Auto Reposting Match Invoice      |
| SIS Auto Update Match Bank Transfer   | SIS Auto Update Match Bank Transfer   |
| SIS Generate Depreciation Asset       | SIS Generate Depreciation Journal     |
| SIS Process Queue DocumentNo          | SIS Process Queue DocumentNo          |
| SIS Close Document PO                 | SIS Close Document PO                 |
| SIS Generate GL Amortization Schedule | SIS Generate GL Amortization Schedule |
| SIS Generate Invoice From Schedule    | SIS Generate Invoice From Schedule    |

Ikuti langkah berikut untuk mengkonfigurasi Scheduler masing-masing proses:

1. Buka menu **Scheduler**.
2. Input **Name** sesuai kebutuhan.
3. Pada field **Process**, input process yang akan dikonfigurasi.
4. Pada field **Schedule**, tentukan jadwal eksekusi (menit, jam, atau hari).
5. Pada field **Days to Keep Log**, tentukan berapa lama log hasil eksekusi disimpan oleh sistem.
6. Klik **Save**.
7. Klik **Not Schedule**.
8. Klik **OK**.