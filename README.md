# 估計國道事故處理時間
在過往研究中，對於事故處理時間之估計，大多係透過建立統計模式，或使用機器學習(Machine Learning)/深度學習(Deep Learning)方法進行估計。
此兩種方法在過往研究都曾有過優秀的表現，然而前者通常需假設處理時間服從特定機率分布(Probability Distribution)，且校估參數繁多；
後者則是在機器學習或深度學習中，常有模式難以解釋(uninterpretable)的問題存在。

因此，本專案的發想除了希望在可容許之誤差下，能準確預估事故處理時間外，
亦期望建立一套易於解釋，且可免除校估眾多參數的方法，以利交通主管機關後續擬定管理政策。
本專案建構一套基於貝氏定理(Bayes' Theorem)之估計國道事故處理時間模式。此模式只需要透過簡單的統計分析及貝氏定理，即可得到不錯的效果。

本專案的原始資料來源為交通部高速公路局的肇事分析系統資料庫，該資料庫目前僅供內部人員使用，故原始資料恕不放上來。
本專案附上的dataset.xlsx則為已整理過後之資料集。

# 事故處理時間之機率分布
我們在後面的統計分析都是使用中位數，並非平均數，原因就在於事故處理時間的機率分布，顯然異於常態分布。
這邊我們放上一張圖，圖中以每5分鐘為一組距，更能看出事故處理時間之分布情形：
<div align="center">
<img src="https://user-images.githubusercontent.com/81426493/236681339-93f5b32e-c8dd-4233-834e-57f274116ba0.png">
</div>
<br>
使用中位數的優點在於它的穩健性(robustness)，不易受極端值影響。
由於事故處理時間的機率分布異於常態分布(雖然此處並沒有真的去檢定，有興趣的讀者可以試試)，
因此若之後要針對事故處理時間進行統計檢定，應當使用非母數檢定方法(Non-parametric Testing Method)。


# 資料處理、分析方法及預估模式
詳細的資料處理、分析及預估方法，請見bayes_classifier.ipynb
