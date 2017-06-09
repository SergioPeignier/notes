#!/bin/bash

TITLE=Sergio-Peignier-Home
AUTHOR=Sergio Peignier
WEBSITEFOLDER=./
#BEFORE="./before-body.html"
#AFTER="./after-body.html"
all: $(WEBSITEFOLDER) $(addprefix $(WEBSITEFOLDER)/, $(addsuffix .html, $(basename $(wildcard *.md))))
$(WEBSITEFOLDER):
	mkdir -p "$(WEBSITEFOLDER)"

$(WEBSITEFOLDER)/%.html: %.md
	# Convert markdown to html5.
	pandoc -Ss -V pagetitle="$(TITLE)" -V author-meta="$(AUTHOR)" -f markdown -t html5 -o "$@" "$<"

		#         -H "$HEADER" -B "$BEFORE" -A "$AFTER" \
		#             -V pagetitle="$TITLE" -V author-meta="$AUTHOR" \
		#                 -f markdown -t html5 -o "$OUT_FILE" "$IN_FILE"
	
	#pandoc -s -f markdown -t html5 -o "$@" "$<"

clean:
	rm -rf $(WEBSITEFOLDER)/*.html
