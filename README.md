diff --git a/README.md b/README.md
index f572ce55bb931a564910bb232d18bb4037e47527..a4fdab1015ec6036b6d820fe844ca74b1c11aa46 100644
--- a/README.md
+++ b/README.md
@@ -1,28 +1,25 @@
 # AVPsim-ver1
 
-This repository provides a minimal SUMO setup to simulate 20 cars that start in a
-parking area and drive toward randomly chosen goal edges.
+このリポジトリは、20台の車が駐車場から出発してランダムに選ばれたゴールに向かう SUMO シミュレーションの最小構成を提供します。
 
-## Preparing the network
-1. Ensure [SUMO](https://www.eclipse.org/sumo/) is installed and `netconvert` and
-   `sumo` are available on your `PATH`.
-2. Generate the network file from the provided node and edge definitions:
+## ネットワークの準備
+1. [SUMO](https://www.eclipse.org/sumo/) をインストールし、`netconvert` と `sumo` が `PATH` から実行できるようにしてください。
+2. 以下のコマンドでネットワークファイルを生成します。
    ```bash
    netconvert -c netconvert_config.nvc
    ```
-   This creates `parking.net.xml`.
+   `parking.net.xml` が作成されます。
 
-## Generating routes
-Random destinations are created each time using the Python script:
+## ルートの生成
+Python スクリプトを実行して毎回ランダムな目的地を設定します。
 ```bash
 python3 generate_routes.py
 ```
-This produces `parking.rou.xml`.
+`parking.rou.xml` が生成されます。
 
-## Running the simulation
-Launch SUMO with the generated configuration:
+## シミュレーションの実行
+生成した設定を使って SUMO を起動します。
 ```bash
 sumo-gui -c parking.sumocfg
 ```
-All 20 cars will depart from their parking spots at time 0 and travel to random
-goal edges.
+20 台の車は時刻 0 に駐車場所から出発し、ランダムなゴールへ向かいます。
