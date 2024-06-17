# Sharing
for share knowledge


# Navicat access database postgre:

Postgres 15 removed datlastsysoid field from pg_database table, so any version prior to Navicat 15.0.29 or 16.1 will raise this error while looking for this deprecated field.

To fix this, either upgrade to the latest Navicat 15.0.29 or 16.1 and up (might require new license), or do this:

Exit Navcat.
Open Navicat folder (usually under C:\Program Files\PremiumSoft\Navicat....), depends on your Navicat edition
Locate libcc.dll and create a backup of this file (copy and paste it as "libcc-backup.dll" or any other name)
Open this file in any HEX editor, you can use online tool such as https://hexed.it/ if you want.
Search for "SELECT DISTINCT datlastsysoid" in the file, and replace it with "SELECT DISTINCT dattablespace"
Save the file in the original location. If you get any security issues, save it as ".txt" file, and then rename it to ".dll"
That's it! Navicat now works as before. If you have ESET or other security tools, the dll file might be locked for few minutes, for security checkup. Be patient, and try after ~5 min again...
Enjoy!
