
cat > sr.py <<'PY'
import speedtest
import socket
import os
import time

def banner():
    os.system("clear")
    print("""
╔══════════════════════════════╗
║       ⚡ SR WIFI SPEED ⚡     ║
╠══════════════════════════════╣
║       WiFi Speed Tester      ║
╚══════════════════════════════╝
""")

banner()

try:
    hostname = socket.gethostname()
    local_ip = socket.gethostbyname(hostname)

    print("[+] Device IP :", local_ip)
    print("[+] Testing your internet speed...")
    print("[+] Please wait...\n")

    st = speedtest.Speedtest()
    st.get_best_server()

    ping = st.results.ping
    download = st.download() / 1_000_000
    upload = st.upload() / 1_000_000

    print("━━━━━━━━━━━━━━━━━━━━━━━━━━━━")
    print(f"📡 Ping     : {ping:.0f} ms")
    print(f"⬇ Download : {download:.2f} Mbps")
    print(f"⬆ Upload   : {upload:.2f} Mbps")
    print("━━━━━━━━━━━━━━━━━━━━━━━━━━━━")
    print("✅ SR Speed Test Complete!")

except Exception as e:
    print("\n❌ Speed test failed.")
    print("Check your internet connection.")
    print("Error:", e)
PY
