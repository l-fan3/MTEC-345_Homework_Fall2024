### 1miniconda environment installed successfullly.


### 2. Data Collection and Labeling:
1.What object type is the variable path?
It is a filesystem path.

2.What object type is stored in the files list?
Path objects,specifically, each item in the files list is a Path object representing a .wav file .

3.Explain the difference between path.exists() and path.is_dir(). Why might both checks be necessary?
path.exist()checks whether the path refers to an existing file or directory in the file system,it doesn't distinguish between types of filesystem objects. 
"path.is-dir()"specifically checks if the path is referring to an existing directory. path.exists() ensures that something is actually there at the specified path, otherwise might try to operate on a non-existent path, and therefore might create errors.

4.Describe the functionality of the rglob() method. How does it differ from the glob() method in pathlib?
"rglob()" is a method for searching for files matching a pattern, it search all directories, but glob() only search current directory.
5.What can you infer about the directory structure from the use of rglob('*.wav')?
"rglob('*.wav')" not only searches for the given directory but also searches its all subdirectories rescursively, so we can infer that all audio files in the folder are not stored in a single flat directory, otherwise a "glob('*.wav')" would have sufficed already.
6.What modifications would be needed to include .mp3 files in the files list?
(*I've asked AI for this one because I have no idea how to achieve it.) ''files = [file for file in path.rglob('*.wav')]''
7.If the goal is to also print the names of all the .wav files collected, how can you achieve this?

8.Why might it be beneficial to initialize the files list before populating it with file paths?