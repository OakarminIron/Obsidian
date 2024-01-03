```python
import os

def rename_music_files(directory):
    for filename in os.listdir(directory):
        if filename.endswith(".mp3"):
            # Split the filename at the first occurrence of ' - '
            parts = filename.split(' - ', 1)
            
            # Check if the filename has the expected format
            if len(parts) == 2:
                new_filename = parts[1]
                
                # Rename the file
                old_path = os.path.join(directory, filename)
                new_path = os.path.join(directory, new_filename)
                
                os.rename(old_path, new_path)
                print(f'Renamed: {filename} -> {new_filename}')

if __name__ == "__main__":
    # Set the music directory to the current script's directory
    music_directory = os.path.dirname(os.path.realpath(__file__))
    
    rename_music_files(music_directory)

```

