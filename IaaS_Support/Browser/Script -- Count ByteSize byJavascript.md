# Count ByteSize by Javascript

functionlengthInUtf8Bytes(str) {  
 // Matches only the 10.. bytes that are non-initial characters in a multi-byte sequence.varm = encodeURIComponent(str).match(/%[89ABab]/g);  
 returnstr.length+ (m ? m.length: 0);  
}

From <[https://stackoverflow.com/questions/5515869/string-length-in-bytes-in-javascript](https://stackoverflow.com/questions/5515869/string-length-in-bytes-in-javascript)>