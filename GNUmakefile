pygmentize	?= pygmentize

STYLES		!= ${pygmentize} -L styles | awk '/:$$/ { gsub(":", ""); print $$2 }'

css_files	:= $(addsuffix .css, ${STYLES})

.PHONY:	all
all:	${css_files}

.PHONY:	${css_files}
${css_files}:
	( \
	echo "/*-" $$(pygmentize -V) "*/"; \
	${pygmentize} -S $(basename $@) -f html -a .highlight \
	) > $@
