import os
import platform
import socket
import shutil
import subprocess

def clear():
    os.system("clear")

def banner():
    print("\033[96m")
    print("╔══════════════════════════════════════╗")
    print("║                                      ║")
    print("║          C Y B E R   S R             ║")
    print("║                                      ║")
    print("╚══════════════════════════════════════╝")
    print("\033[0m")
    print("  CYBER SR :: Termux Utility")
    print("  Mode :: SAFE / EDUCATIONAL")
    print()

def system_info():
    clear()
    banner()
    print("[1] System Information")
    print("[2] Storage Information")
    print("[3] Network Information")
    print("[4] Device Hostname")
    print("[0] Back")

def show_system():
    print("\n--- SYSTEM INFO ---")
    print("OS       :", platform.system())
    print("Release  :", platform.release())
    print("Machine  :", platform.machine())
    print("Python   :", platform.python_version())

def show_storage():
    total, used, free = shutil.disk_usage("/")
    print("\n--- STORAGE ---")
    print(f"Total : {total // (1024**3)} GB")
    print(f"Used  : {used // (1024**3)} GB")
    print(f"Free  : {free // (1024**3)} GB")

def show_network():
    print("\n--- NETWORK INFO ---")
    try:
        hostname = socket.gethostname()
        ip = socket.gethostbyname(hostname)
        print("Hostname :", hostname)
        print("Local IP :", ip)
    except:
        print("Network information unavailable.")

def main():
    while True:
        clear()
        banner()

        print("╔══════════════════════════════════════╗")
        print("║        ⚡ CYBER SR TOOLS ⚡           ║")
        print("╠══════════════════════════════════════╣")
        print("║ [1] 🖥 System Info                  ║")
        print("║ [2] 💾 Storage Info                 ║")
        print("║ [3] 🌐 Network Info                 ║")
        print("║ [4] 📱 Device Info                  ║")
        print("║ [5] 🔄 Refresh                      ║")
        print("║ [0] 🚪 Exit                         ║")
        print("╚══════════════════════════════════════╝")

        choice = input("\nroot@cyber-sr:~$ ")

        if choice == "1":
            clear(); banner(); show_system()
            input("\nPress Enter...")
        elif choice == "2":
            clear(); banner(); show_storage()
            input("\nPress Enter...")
        elif choice == "3":
            clear(); banner(); show_network()
            input("\nPress Enter...")
        elif choice == "4":
            clear(); banner()
            print("Device :", platform.node())
            print("System :", platform.system())
            input("\nPress Enter...")
        elif choice == "5":
            continue
        elif choice == "0":
            print("\nCYBER SR shutting down...")
            break
        else:
            print("\nInvalid option!")
            input("Press Enter...")

if __name__ == "__main__":
    main()
