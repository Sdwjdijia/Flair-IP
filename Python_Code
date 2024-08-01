import tkinter as tk
from tkinter import messagebox
import socket

def get_ip_address():
    url = entry.get()
    try:
        # 獲取域名（去除 'http://' 或 'https://' 前綴）
        hostname = url.replace("http://", "").replace("https://", "").split('/')[0]
        # 使用 socket 模組獲取 IP 地址
        ip_address = socket.gethostbyname(hostname)
        result = f"網址 {url} 的 IP 地址是: {ip_address}"
        
        # 顯示結果
        messagebox.showinfo("IP 地址", result)
        
        # 將結果寫入 TXT 文件
        with open("ip_address_results.txt", "a") as file:
            file.write(result + "\n")
    except socket.gaierror as e:
        messagebox.showerror("錯誤", f"無法取得 IP 地址: {e}")

# 建立主窗口
root = tk.Tk()
root.title("IP 地址查詢")

# 建立輸入欄位
label = tk.Label(root, text="輸入網址:")
label.pack(pady=5)
entry = tk.Entry(root, width=50)
entry.pack(pady=5)

# 建立查詢按鈕
button = tk.Button(root, text="查詢 IP 地址", command=get_ip_address)
button.pack(pady=20)

# 運行主循環
root.mainloop()
