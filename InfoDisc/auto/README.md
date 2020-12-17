Folder for bot features to automate information discovery tasks. </ br>
# Automated tasks
## Forceful Browsing Targeted Wordlist
Design stepthrough 
<ol>
  <li>accept URL and flags as input</li>
  <li>User enters appropriate flag to pull from subpaths and/or root domain of URL</li>
  <li>web scrape site(s)</li>
  <li>Create .txt file in current directory</li>
  <li>write scrapped words, one per line, to txt file until complete</li>
  <li>Inform user file is complete by telling them how many lines were written to the pilfered.txt
  <li>Create new txt file</li>
  <li>write scrapped words into new file as paths, building paths up to 8 directories deep</li>
  <li>Inform user file is copmleted by telling them how many lines were written to directories.txt</li>
</ol>

Flag options
<ol>
  <li>-h lists basic usages directions in 1 line & all flags, eac in a subsequent line</li>
  <li>-d x to manually define to many directories deep of paths should be written to the directories.txt file, overrides default setting of 8</li>
  <li>-s x to specify how many subpaths to search and pull words from</li>
  <li>-r to include pulling words from the root domain of the given url</li>
  <li>-u followed by location of wordlist to pull from multiple URLs listed one line at a time in said wordlist</li>
</ol>
Validating inputs
<ol>
  <li>URLs must be valid</li>
  <li>Flag must be valid</li>
  <li>All other input must be rejected</li>
</ol>
Errors
<ol>
  <li>if URL is invalid, stop and return error</li>
  <li>if URL cannot be reached, stop and return error</li>
  <li>if invalid flag is used, stop and return -h flag info as if that had been entered</li>
  <li>if any special characters are used except for - return nice try and stop</li>
  <li>if any unexpected input is used fail and stop</li>
  <li>if webscrapping fails unexpectedly stop and report failure</li>
  <li>if file creation fails stop and report failure</li>
  <li>if file write fails stop and report failure</li>
  <li>if file read fails stop and report failure</li>
  <li>if executable fails stop and report failure</li>
  <li>create time-out options where if nothing is currenlty in process for x amount of time, report timeout error</li>
  <li>after x amount of timeout errors stop</li>
 </ol>
 
## New Tools coming soon
