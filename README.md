# QUIC PROTOCOL

‫
המימוש‬ ‫כולל‬ ‫העברה‬ ‫של‬ ‫מספר‬ ‫קבצים‬ ‫מהשרת‬ ‫ללקוח‬ ‫לפי‬ ‫בקשת‬ ‫הלקוח‪.‬‬
‫כל ‬‫קובץ‬ ‫ישוייך‬ ‫ל‬ ‫‪ stream‬‬‫ייחודי‬ ‫אשר‬ ‫תפקידו‬ ‫יהיה‬ ‫לקרוא‬ ‫מהקובץ‬ ‫בצד‬ ‫השרת‪,‬‬ ‫ולכתוב‬ ‫לקובץ‬
‫בצד ‬‫הלקוח‪.‬‬
‫כל ‬‫אחד‬ ‫מה‬ ‫‪streams‬‬‫‪,‬‬‫ייכנס‬ ‫תחת‬ ‫‪frame‬‬ ‫אותו‬ ‫אנו‬ ‫נשלח‬ ‫על‬ ‫גביי‬ ‫הקשר‪.‬‬
‫ה‬‫‪frame‬‬ ‫הזה‪-‬‬ ‫ייכנס‬ ‫ל‬ ‫‪socket‬‬ ‫של‬ ‫הפרוטוקול‬ ‫‪QUIC‬‬ ‫‪,‬‬ ‫והוא‬ ‫יישלח‬ ‫ללקוח‪.‬‬
‫לכל‬‫‪Stream‬‬ ‫‪,‬‬‫יוגרל‬ ‫מספר‬ ‫בין‬ ‫‪1000‬‬ ‫ל‬ ‫‪2000‬‬ ‫בצורה‬ ‫אקראית‪-‬‬ ‫והוא‬ ‫יקבע‬ ‫את‬ ‫גודל‬ ‫הזרמים‬ ‫שעוברים‬
‫בבתים‬‫(‬ ‫‪Bytes‬‬‫)‬‫בפעם‬ ‫הזו‬ ‫עד‬ ‫סוף‬ ‫הקשר‬ ‫בין‬ ‫השרת‬ ‫ללקוח‪.‬‬
‫מימוש‬‫ריבוי‬ ‫הזרמים‬ ‫שלנו‬ ‫התבצע‬ ‫באמצעות‬ ‫שימוש‬ ‫במספר‬ ‫תהליכונים‬ ‫(‬ ‫‪threads‬‬‫)‬‫ועל‬ ‫כך‬ מפורט בקובץ הPDF.

This project implements the QUIC protocol. The protocol will be based on the UDP protocol and the QUIC library in Python is not used. In this code there is an emphasis on the ability of the protocol - "multiple streams".
The implementation includes the transfer of several files from the server to the client according to the client's request.
Each file will be associated with a unique stream whose role will be to read from the file on the server side, and write to the file
on the client side.
Each of the streams will be entered under a frame that we will send over the connection. ‬
This frame will enter the socket of the QUIC protocol, and it will be sent to the client. ‬‬
For each Stream, a number between 1000 and 2000 will be drawn randomly - and it will be determined the size of the currents that pass
In bytes this time until the end of the connection between the server and the client.


