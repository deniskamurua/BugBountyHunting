subfinder -d HOST >> FILE; assetfinder --subs-only HOST >> FILE; amass enum 
-norecursive -noalts -d HOST >> FILE ; subjack -w FILE -t 100 -timeout 30 -ssl
-c $GOPATH/scr/github.com/haccer/subjack/fingerprints.json -v 3 >> takeover;
