# class SongNode:
    def __init__(self, title):
        self.title = title
        self.next = None

class Playlist:
    def __init__(self):
        self.head = None
    
    def insert_Song(self, title):
        new_Song = SongNode(title)
        if not self.head:
            self.head = new_Song
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_Song
        print(f"Song '{title}' added.")
    
    def delete_Song(self, title):
        current = self.head
        prev = None
        while current:
            if current.title == title:
                if prev:
                    prev.next = current.next
                else:
                    self.head = current.next
                print(f"Song '{title}' deleted.")
                return
            prev = current
            current = current.next
        print(f"Song '{title}' not found.")
    
    def display_playlist(self):
        if not self.head:
            print("Playlist is empty.")
            return
        
        current = self.head
        count = 1
        while current:
            print(f"{count}. {current.title}")
            current = current.next
            count += 1

def main():
    playlist = Playlist()
    while True:
        print("\nMenu:")
        print("1. Add Song")
        print("2. Delete Song")
        print("3. Display Playlist")
        print("4. Exit")

        choice = input("Enter your choice (1-4): ")
        if choice == '1':
            song_title = input("Enter the song title to add: ")
            playlist.insert_Song(song_title)
        elif choice == '2':
            song_title = input("Enter the title to delete: ")
            playlist.delete_Song(song_title)
        elif choice == '3':
            playlist.display_playlist()
        elif choice == '4':
            print("Exiting Program.")
            break
        else:
            print("Invalid choice, try again")

if __name__ == "__main__":
    main()
Menu:
1. Add Song
2. Delete Song
3. Display Playlist
4. Exit
Enter your choice (1-4): 1
Enter the song title to add: Bohemian Rhapsody
Song 'Bohemian Rhapsody' added.

Menu:
1. Add Song
2. Delete Song
3. Display Playlist
4. Exit
Enter your choice (1-4): 1
Enter the song title to add: Hotel California
Song 'Hotel California' added.

Menu:
1. Add Song
2. Delete Song
3. Display Playlist
4. Exit
Enter your choice (1-4): 3
1. Bohemian Rhapsody
2. Hotel California

Menu:
1. Add Song
2. Delete Song
3. Display Playlist
4. Exit
Enter your choice (1-4): 2
Enter the title to delete: Bohemian Rhapsody
Song 'Bohemian Rhapsody' deleted.

Menu:
1. Add Song
2. Delete Song
3.