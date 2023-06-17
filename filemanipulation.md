## File and stream I/O
File and stream I/O (input/output) refers to the transfer of data either to or from a storage medium.
Most popular file and directory classes:
-	File - provides static methods for creating, copying, deleting, moving, and opening files, and helps create a FileStream object.
-	FileInfo - provides instance methods for creating, copying, deleting, moving, and opening files, and helps create a FileStream object.
-	Directory - provides static methods for creating, moving, and enumerating through directories and subdirectories.
-	DirectoryInfo - provides instance methods for creating, moving, and enumerating through directories and subdirectories.
-	Path - provides methods and properties for processing directory strings in a cross-platform manner.
#### streams support:
-	Reading
-	Writing
-	Seeking
#### Isolated storage:
Isolated storage is a data storage mechanism that provides isolation and safety by defining standardized ways of associating code with saved data.

## write to a file:
There are multiple ways to write a text to a file in .NET.
Most used classes and methods to write text to a file:
-	StreamWriter contains methods to write to a file synchronously (Write and WriteLine) or asynchronously (WriteAsync and WriteLineAsync).
-	File provides static methods to write text to a file such as WriteAllLines and WriteAllText, or to append text to a file such as AppendAllLines, AppendAllText, and AppendText.
-	Path is for strings that have file or directory path information. It contains the Combine method and in .NET Core 2.1 and later, the Join and TryJoin methods. These methods let you concatenate strings for building a file or directory path.
### read to a file:
There are two classes that are used to read and write data:
-	System.IO.BinaryWriter
The BinaryWriter class provides methods that simplify writing primitive data types to a stream. For example, you can use the Write method to write a Boolean value to the stream as a one-byte value.
-	System.IO.BinaryReader
The BinaryReader class provides methods that simplify reading primitive data types from a stream. For example, you can use the ReadBoolean method to read the next byte as a Boolean value and advance the current position in the stream by one byte.

