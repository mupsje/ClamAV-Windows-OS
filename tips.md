ClamAV is an open source Anti-Virus that that can accept virus signatures from different contributors. Swinburne University is kind enough to contribute additional signatures for ClamAV.

Following steps demonstrate how to improve the signatures in your existing ClamAV installation. These instruction assume you're using ClamAV on a Linux machine.

  - Locate `/clamav/freshclam.conf` file.
  - Add the following lines at the end of the file:
    ```
    DatabaseCustomURL http://ftp.swin.edu.au/sanesecurity/foxhole_generic.cdb
    DatabaseCustomURL http://ftp.swin.edu.au/sanesecurity/foxhole_filename.cdb
    DatabaseCustomURL http://ftp.swin.edu.au/sanesecurity/foxhole_all.cdb
    DatabaseCustomURL http://ftp.swin.edu.au/sanesecurity/foxhole_js.cdb
    DatabaseCustomURL http://ftp.swin.edu.au/sanesecurity/badmacro.ndb
    DatabaseCustomURL http://ftp.swin.edu.au/sanesecurity/bofhland_malware_attach.hdb
    ```

  - Restart freshclam.
