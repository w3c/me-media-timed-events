dest = /home/ashimura/public_html/www.w3.org/WWW/TR/2019/NOTE-media-timed-events-20190404

### For Echidna
#document = https://w3c.github.io/wot-thing-description/publication/wd3/manifest.txt
#decision = https://www.w3.org/2018/09/12-wot-minutes.html
#token = 19281487755bcb45bb5ed301.41712616


tidy:
	tidy -i -m index.html
#	tidy -i -m -asxml index.html

overview_diff:
	htmldiff.sh ${prev_overview} Overview.html > overviewdiff.html

#snapshotdiff:
#	htmldiff.sh index.snapshot.html Overview.html > snapshotdiff.html

diff:
	htmldiff.sh $(prev)/Overview.html Overview.html > diff.html

srcdiff:
	diff $(prev)/Overview.html Overview.html > srcdiff

install:
	cp index.html diff.html $(dest)/Overview.html

raw:
	diff index.snapshot.html Overview.html

publish:
	curl 'https://labs.w3.org/echidna/api/request' --data 'url=$(document)&decision=$(decision)&token=$(token)'
#	curl 'https://labs.w3.org/echidna/api/request' --data 'url=$(document)&decision=$(decision)&token=$(token)' -d 'dry-run=true'	

