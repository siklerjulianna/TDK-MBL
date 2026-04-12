# TDK-MBL
A Makrofaktor-Black-Litterman-modell kódjai

Az esettanulmányokhoz tartozó kódok két részből állnak. Az adatbázis készítő kódok (brazil esetben 1, amerikai esetben 3) a makrofaktorok és előrejelzések nyers adatainak feldolgozását és az adattisztítást végzik. Az analízis kódok az értékpapírok adatsorait töltik le és illesztik össze a teljes adatbázist, valamint végzik az optimalizációt, kiértékelést és adatvizualizációt.
A programkódok Python notebookok (.ipynb), Google Colab-ban készítve, ezért javasolt őket ugyanebben a környezetben futtatni. A FRED adatbázis eléréséhez API kulcs szükséges, amelyet futtatás előtt a Google Colab _Secrets_ (titkos kódok) részében kell megadni MY_FRED néven. FRED API kulcs rövid regisztrációt követően itt igényelhető: https://fredaccount.stlouisfed.org/apikeys

Az optimalizáláshoz a kifejezetten komplex problémák megoldásához való CVXPY csomagot és a CLARABEL belső pontos solvert használtam, amely stabil numerikus hátteret biztosít a kvadratikus optimalizálási feladatokhoz. A számítási stabilitás érdekében 0,1%-os alsó korlátot vezettem be a nézetek szórásaira, hogy a bizonytalanság mátrix determinánsa ne legyen nulla, tehát invertálható legyen. Abban a néhány esetben, amikor a solver nem talál megoldást, ideiglenesen megemeljük a kockázati korlátot, hogy a modell extrém piaci körülmények között is működőképes maradjon.
