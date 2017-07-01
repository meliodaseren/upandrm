# Test Shell Script Auto add/commit/push

Inline `code` has `back-ticks around` it.

``There is a literal backtick (`) here.``

```Shell
#! /bin/bash

cd /e/GitHub/upandrm

while true
do
	fc="$(ls pic | wc -l)" # count file in /pic
	if [ $fc -gt 0 ];      # $fc > 0
		then
		FILES=/e/GitHub/upandrm/pic/*
		for f in $FILES
		do
			/mingw64/bin/git add $f
			/mingw64/bin/git commit -m "$(date +%H-%M-%S)"
			/mingw64/bin/git remote add origin git@github.com:meliodaseren/upandrm.git
			/mingw64/bin/git push -u origin master
			/mingw64/bin/git remote remove origin
		done
	fi;
	rm -rf /e/GitHub/upandrm/pic/*
	sleep 3
done
```
