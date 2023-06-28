import tkinter as tk
from tkinter import messagebox
import subprocess

def install_docker():
    subprocess.run(["yum", "install", "docker", "-y"])
    messagebox.showinfo("Docker Installation", "Docker installed successfully!")

def run_container():
    container_name = container_entry.get()
    subprocess.run(["docker", "run", "-it", container_name])

def show_images():
    result = subprocess.run(["docker", "images"], capture_output=True, text=True)
    messagebox.showinfo("Docker Images", result.stdout)

def show_running_containers():
    result = subprocess.run(["docker", "ps"], capture_output=True, text=True)
    messagebox.showinfo("Running Containers", result.stdout)

def start_container():
    container_name = container_entry.get()
    subprocess.run(["docker", "start", container_name])
    messagebox.showinfo("Start Container", f"Container {container_name} started successfully!")

def stop_container():
    container_name = container_entry.get()
    subprocess.run(["docker", "stop", container_name])
    messagebox.showinfo("Stop Container", f"Container {container_name} stopped successfully!")

def remove_container():
    container_name = container_entry.get()
    subprocess.run(["docker", "rmi", container_name, "--force"])
    messagebox.showinfo("Remove Container", f"Container {container_name} removed successfully!")

# Create the main window
window = tk.Tk()
window.title("Docker Menu")

# Welcome label
welcome_label = tk.Label(window, text="WELCOME TO MY DOCKER MENU", font=("Helvetica", 16, "bold"))
welcome_label.pack(pady=10)

# Menu options
menu_options = [
    ("Install Docker", install_docker),
    ("Run a New Container", run_container),
    ("See Existing Images", show_images),
    ("See Running Containers", show_running_containers),
    ("Start a Container", start_container),
    ("Stop a Container", stop_container),
    ("Remove a Container", remove_container)
]

# Create buttons for each option
for option_text, option_command in menu_options:
    button = tk.Button(window, text=option_text, command=option_command, width=30)
    button.pack(pady=5)

# Container entry
container_entry_label = tk.Label(window, text="Container Name:", font=("Helvetica", 12))
container_entry_label.pack(pady=10)
container_entry = tk.Entry(window, width=30)
container_entry.pack()

# Start the main loop
window.mainloop()
