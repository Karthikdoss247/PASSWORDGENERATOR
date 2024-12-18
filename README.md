# PASSWORDGENERATOR
import tkinter as tk
from PIL import Image, ImageTk  
import random
import string

def generate_password():
    password = ''.join(random.choices(string.ascii_letters + string.digits, k=8))
    password_entry.delete(0, tk.END)
    password_entry.insert(0, password)

root = tk.Tk()
root.title("Password Generator")
root.geometry("400x300")

#bg_image = Image.open(r"C:\Users\User\Desktop\pass.jpg")  
#bg_photo = ImageTk.PhotoImage(bg_image)

canvas = tk.Canvas(root)
canvas.pack(fill="both", expand=True)

#canvas.create_image(0, 0, image=bg_photo, anchor="nw")

frame = tk.Frame(root, bg="#ffffff", bd=5, relief="ridge")
frame.place(relx=0.5, rely=0.5, anchor="center")

title_label = tk.Label(frame, text="Secure Password Generator", font=("Arial", 16, "bold"), bg="#ffffff", fg="#006064")
title_label.pack(pady=10)

password_label = tk.Label(frame, text="Generated Password:", font=("Arial", 12), bg="#ffffff", fg="#004d40")
password_label.pack(pady=5)

password_entry = tk.Entry(frame, width=30, font=("Arial", 12), borderwidth=3, relief="sunken")
password_entry.pack(pady=5)

generate_button = tk.Button(frame, text="Generate Password", font=("Arial", 12, "bold"), bg="#00796b", fg="white", activebackground="#004d40", activeforeground="white", command=generate_password)
generate_button.pack(pady=15)

root.mainloop()
