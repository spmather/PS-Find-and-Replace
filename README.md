# PS-Find-and-Replace
PowerShell find and replace function



.SYNOPSIS

Uses find and replace function to speedily redact sensitive data.


.DESCRIPTION

This function is intended to be a single find and replace function with the use of
regex or strings to find and replace sensitive data.  For example, with use in an
environment where you need to redact IP addresses from a log.


.EXAMPLE

Find unique string
Invoke-FindandReplace -FilePath ./Simulated_Senstive_Documents/Simulated_Sensitive_Log.txt -Find 'Secret' -Unique

Find and replace
$FilePath = "./Simulated_Senstive_Documents/Simulated_Sensitive_Log.txt"
Invoke-FindandReplace $FilePath -Find 'Secret' -Replace 'Redacted'

Bulk find and replace (note:  For substutution cypher, please use Format-ScrambledEggs)
$CSV = Import-Csv ./example.csv
ForEach ($Line in $CSV) {Invoke-FindandReplace $FilePath -Find $CSV.Find -Replace $CSV.Replace}

