# Dinner Battle（美食對戰系統）

中興大學美食對戰系統：雙人配對後各自選擇剪刀/石頭/布與餐廳，依猜拳結果決定今天吃哪家餐廳。後端以 Flask + Flask-SocketIO 提供配對、即時對戰與歷史紀錄功能，並以自製資料結構管理玩家與餐廳資料（玩家：2-3-4 樹；餐廳：AVL 樹；配對：Queue）。

## 技術棧
- Python (Flask, Flask-SocketIO, Flask-CORS, pandas)
- HTML / Socket.IO（前端 `index.html`）

## 主要檔案
- `server.py`：Flask + Socket.IO 伺服器，提供註冊/登入、配對、對戰、歷史紀錄 API
- `player.py`：玩家資料結構（2-3-4 樹）
- `restaurant.py`：餐廳資料結構（AVL 樹），依星數與留言數計算評分
- `queue_system.py`：配對佇列
- `game_logic.py`：剪刀石頭布勝負判定

## 資料集
- `restaurants.csv`：手動蒐集的中興大學周邊餐廳清單（約 36 間），欄位為店名、星數、留言數，供對戰時隨機抽選餐廳使用。

## 執行方式
```bash
pip install flask flask-socketio flask-cors pandas
python server.py
```
伺服器預設啟動於 `http://localhost:5000`。
