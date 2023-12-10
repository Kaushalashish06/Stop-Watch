# Stop-Watch

import time

class Stopwatch:
    def __init__(self):
        self.start_time = None
        self.is_running = False

    def start(self):
        if not self.is_running:
            self.start_time = time.time()
            self.is_running = True
            print("Stopwatch started.")

    def stop(self):
        if self.is_running:
            elapsed_time = time.time() - self.start_time
            self.is_running = False
            print(f"Stopwatch stopped. Elapsed time: {elapsed_time:.2f} seconds")

    def reset(self):
        self.start_time = None
        self.is_running = False
        print("Stopwatch reset.")

if __name__ == "__main__":
    stopwatch = Stopwatch()

    while True:
        print("\n1. Start\n2. Stop\n3. Reset\n4. Exit")
        choice = input("Enter your choice (1/2/3/4): ")

        if choice == "1":
            stopwatch.start()
        elif choice == "2":
            stopwatch.stop()
        elif choice == "3":
            stopwatch.reset()
        elif choice == "4":
            print("Exiting the stopwatch.")
            break
        else:
            print("Invalid choice. Please enter 1, 2, 3, or 4.")
