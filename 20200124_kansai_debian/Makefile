
all:
	dot -Tpng -o lambda_arch01.png lambda_arch01.dot
	dot -Tpng -o lambda_arch02.png lambda_arch02.dot
	dot -Tpng -o lambda_arch03.png lambda_arch03.dot
	dot -Tpng -o lambda_arch.png lambda_arch.dot
	pandoc -t beamer main.md metadata.yml -o out.pdf --pdf-engine=lualatex \
	       -V mainfont=IPAGothic -V theme:Warsaw -V aspectratio:43
