Because GitHub doesn’t display .scpt files, the code for the three scripts in this repository is reproduced below (as of 2025-12-26).


```scpt
-- Find a Chrome tab for a Udemy course and fast forward the video 

tell application "Google Chrome"
	set windowTabList to title of tabs of every window
	set targetTitle to "Course: "
	set found to false
	set windowIndex to 1
	repeat with thisWindowsTabs in windowTabList
		set TabIndex to 1
		repeat with TabTitle in thisWindowsTabs
			if (TabTitle as text) contains targetTitle then
				set index of window windowIndex to 1
				set active tab index of window 1 to TabIndex
				set found to true
				tell window 1's active tab to execute javascript "
		                    var forwardSkipButton = document.querySelector('button[data-purpose=\"forward-skip-button\"]');
              			forwardSkipButton.click();
                		"
				exit repeat
			end if
			set TabIndex to TabIndex + 1
		end repeat
		if found then exit repeat
		set windowIndex to windowIndex + 1
	end repeat
	if not found then
		display dialog "Tab not found."
	end if
end tell
```


```scpt
-- Find a Chrome tab for a Udemy course and play or pause the video 

tell application "Google Chrome"
	set windowTabList to title of tabs of every window
	set targetTitle to "Course: "
	set found to false
	set windowIndex to 1
	repeat with thisWindowsTabs in windowTabList
		set TabIndex to 1
		repeat with TabTitle in thisWindowsTabs
			if (TabTitle as text) contains targetTitle then
				set index of window windowIndex to 1
				set active tab index of window 1 to TabIndex
				set found to true
				tell window 1's active tab to execute javascript "
		                    var playButton = document.querySelector('button[data-purpose=\"play-button\"]');
              		      var pauseButton = document.querySelector('button[data-purpose=\"pause-button\"]');
		                    if (playButton) {
              				playButton.click();
	                    		} else if (pauseButton) {
                        			pauseButton.click();
                    			}
                		"
				exit repeat
			end if
			set TabIndex to TabIndex + 1
		end repeat
		if found then exit repeat
		set windowIndex to windowIndex + 1
	end repeat
	if not found then
		display dialog "Tab not found."
	end if
end tell
```


```scpt
-- Find a Chrome tab for a Udemy course and rewind the video 

tell application "Google Chrome"
	set windowTabList to title of tabs of every window
	set targetTitle to "Course: "
	set found to false
	set windowIndex to 1
	repeat with thisWindowsTabs in windowTabList
		set TabIndex to 1
		repeat with TabTitle in thisWindowsTabs
			if (TabTitle as text) contains targetTitle then
				set index of window windowIndex to 1
				set active tab index of window 1 to TabIndex
				set found to true
				tell window 1's active tab to execute javascript "
		                    var forwardSkipButton = document.querySelector('button[data-purpose=\"forward-skip-button\"]');
              			forwardSkipButton.click();
                		"
				exit repeat
			end if
			set TabIndex to TabIndex + 1
		end repeat
		if found then exit repeat
		set windowIndex to windowIndex + 1
	end repeat
	if not found then
		display dialog "Tab not found."
	end if
end tell

```

