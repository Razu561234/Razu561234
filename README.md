## Hi there 👋
import os
import sys
from colorama import Fore, Style, init

init(autoreset=True)

def clear_screen():
    os.system('clear' if os.name == 'posix' else 'cls')

def draw_banner():
    clear_screen()
    banner = f"""
{Fore.CYAN}====================================================
  ____  ____    ____      _    _____ _   _ 
 |  _ \|  _ \  |  _ \    / \  |___  | | | |
 | |_) | |_) | | |_) |  / _ \    / /| | | |
 |  _ <|  _ <  |  _ <  / ___ \  / / | |_| |
 |_| \_|_| \_\ |_| \_\/_/   \_\/_/   \___/ 
====================================================
{Fore.YELLOW}[+] Tool Name : RS.RAZU
[+] Environment: Termux / Linux
{Fore.CYAN}===================================================={Style.RESET_ALL}
"""
    print(banner)

def main_menu():
    while True:
        draw_banner()
        print(f"{Fore.GREEN}[1]{Fore.WHITE} Check Network Interface & IP")
        print(f"{Fore.GREEN}[2]{Fore.WHITE} Test Ping / Latency")
        print(f"{Fore.GREEN}[3]{Fore.WHITE} View System Specs")
        print(f"{Fore.GREEN}[4]{Fore.WHITE} Exit\n")
        
        choice = input(f"{Fore.RED}[root@RS-RAZU]-[{Fore.WHITE}~{Fore.RED}] $ {Style.RESET_ALL}").strip()

        if choice == '1':
            print(f"\n{Fore.YELLOW}[*] Displaying network interfaces...{Style.RESET_ALL}")
            os.system('ifconfig || ip addr')
            input("\nPress Enter to return...")
        elif choice == '2':
            target = input(f"\n{Fore.YELLOW}Enter target address (default: 8.8.8.8): {Style.RESET_ALL}").strip()
            if not target:
                target = "8.8.8.8"
            os.system(f'ping -c 4 {target}')
            input("\nPress Enter to return...")
        elif choice == '3':
            print(f"\n{Fore.YELLOW}[*] System details:{Style.RESET_ALL}")
            os.system('uname -a')
            input("\nPress Enter to return...")
        elif choice == '4':
            print(f"\n{Fore.CYAN}Exiting RS.RAZU tool...{Style.RESET_ALL}")
            sys.exit(0)
        else:
            input(f"\n{Fore.RED}Invalid option! Press Enter to try again.{Style.RESET_ALL}")

if __name__ == "__main__":
    main_menu()
<!--
**Razu561234/Razu561234** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
