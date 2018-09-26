# class mip::Stream 
A class that defines the interface between the mip sdk and stream based content.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public int64_t Read(uint8_t* buffer, int64_t bufferLength)  |  Read into a buffer from the stream.
 public int64_t Write(const uint8_t* buffer, int64_t bufferLength)  |  Write into the stream from a buffer.
 public bool Flush()  |  flush the stream.
 public void Seek(int64_t position)  |  Seek specific position within the stream.
 public bool CanRead() const  |  A check if stream is readable.
 public bool CanWrite() const  |  A check if stream is writeable.
 public int64_t Position()  |  Get the current position within the stream.
 public int64_t Size()  |  Get the size of the content within the stream.
 public void Size(int64_t value)  |  Set the stream size.
  
## Members
  
### Read
Read into a buffer from the stream.

Parameters:  
* **buffer**: pointer to a buffer 


* **bufferLength**: buffer size. 



  
**Returns**: Number of bytes actually read.
  
### Write
Write into the stream from a buffer.

Parameters:  
* **buffer**: pointer to a buffer 


* **bufferLength**: buffer size. 



  
**Returns**: Number of bytes actually written.
  
### Flush
flush the stream.

  
**Returns**: True if successful else false.
  
### Seek
Seek specific position within the stream.

Parameters:  
* **position**: to seek into stream.


  
### CanRead
A check if stream is readable.

  
**Returns**: True if readable else false.
  
### CanWrite
A check if stream is writeable.

  
**Returns**: True if writeable else false.
  
### Position
Get the current position within the stream.

  
**Returns**: Position within the stream.
  
### Size
Get the size of the content within the stream.

  
**Returns**: The stream size.
  
### Size
Set the stream size.

Parameters:  
* **stream**: size.

