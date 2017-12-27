# plex_db_backup
Backup Plex Database and Preferences

If you need to start from scratch with a clean Plex database, it is time consuming
to enter in all your account/library/DVR settings manually.

This Perl script saves database settings to an xml file which can be restored in the
event of a database corruption.

Before executing, it checks to see if Plex is actively streaming and won't continue
unless it is forced.  Plex is shutdown before beginning and all operations are made
to a copy of the database.  In the case of 'restore' original files are copied to a
backup before restoration.

-backup        Backup the accounts/library/DVR settings to:
                  $dir_backup/$xml_backup
               Backup the Preferences.xml file to:
                  $dir_backup/Preferences.xml
-restore       Restore the settings saved in the backup ($dir_backup)
                  Original files are renamed.
-verbose       More information during the run.
-debug         Won't delete the temporary copy of the database being used for all
               the script modification work.
-force         Shutdown Plex even if it is actively streaming/being used.



Installation/Usage:

Install the XML::Dumper Perl module:
  cpan
    install XML::Dumper

Place the script anywhere, edit the 'customized by user' variables

Call with:  plex_db_backup -backup
