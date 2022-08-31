# holiday-package-project
Save readme to summarize Stage 1 through Stage 3

Langkah-langkah yang kami lakukan pada stage 1 adalah menggali sebanyak mungkin insights dan memperbaikinya di stage 2 (preprocessing). Adapun hasilnya sebagai berikut:
- Handle missing values sebesar 15.35% dengan imputasi median pada data numerik dan imputasi mode pada data kategorikal
- Drop feature:
  - NumberOfChildrenVisiting = Karena terdapat multikolinearitas
  -  CustomerID = Kolom ini berisi value yang unique sehingga tidak akan membantu pemodelan
- Handle value tidak rasional 
  - Gender : Mengganti value “Fe Male” menjadi “Female”.
  - MonthlyIncome : Menghapus baris data dengan value yang kurang dari SAR 9000
  - MaritalStatus : Mengganti value “unmarried” menjadi “single” untuk mengurangi ambiguitas
- Drop 99 duplicate values
- Handle outliers menggunakan pendekatan IQR
- Feature scalling dengan Standardization
  - MonthlyIncome
  - NumberOfTrips
- Feature Encoding
  - TypeofContact (Label Encoding)
  - Gender (Label Encoding)
  - Occupation (One-Hot Encoding)
  - ProductPitched (One-Hot Encoding)
  - MaritalStatus (One-Hot Encoding)
  - Designation (One-Hot Encoding)
- Handle imbalance class pada target "ProdTaken" dengan oversampling SMOTE
- Feature Extraction 
  - Penambahan feature AgeStructure yang berasal dari feature Age
- Feature Selection menggunakan uji ANOVA, sehingga didapat 27 feature (termasuk feature yang telah melalui tahap feature encoding dan feature extraction)

Stage 3
- Modeling yang dilakukan: 
  - Logistic Regression = Hal ini karena target masih dua unique values yang merupakan masih dalam keunggulan logistic regression.
  - KNN = KNN merupakan algoritma klasifikasi yang memiliki keunggulan karena komputasi yang tidak rumit dan diunggulkan apabila dataset tidak terlalu besar.
  - Decision Tree = Algoritma decision tree cocok untuk dataset yang memiliki feature yang dominan di kategorikal, seperti dataset yang saat ini sedang digunakan.
  - Random Forest = Algoritma random forest mirip dengan decision tree, namun lebih baik mencegah overfitting.
  - XGBoost Classifier = Algoritma ini merupakan salah satu yang paling powerful dan cukup detail, karena iterasi yang dilakukan di setiap tree nya lebih mendalam.


Selain itu, alasan pemilihan model di atas karena semua algoritma tersebut cocok untuk task supervised klasifikasi. Sehingga mendorong kami untuk menemukan hasil terbaik. 
