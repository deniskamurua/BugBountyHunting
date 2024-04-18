 export LHOST="URL"; gau $1 redirect | qsreplace "$LHOST" | xargs -I % -P 25 sh -c 'curl -Is "%" 2>&1 | grep -q "locaton: $LHOST" && echo "VULN! %"'
