default:
	f2py -m iri_fcore -h iri_fcore.pyf iri_fcore.f90
	gfortran -c -fPIC iri_fcore.f90 irisub.for irifun.for iritec.for iridreg.for igrf.for cira.for iriflip.for -O3 -w
	f2py -c iri_fcore.pyf iri_fcore.o irisub.o irifun.o iritec.o iridreg.o igrf.o cira.o iriflip.o
	rm ./*.o ./*.mod
	mv iri_fcore*.so ../

test:
	#f2py -m iri_core -h iri_core.pyf iri_fcore.f90
	f2py -c iri_fcore.pyf iri_fcore.f90 irisub.for irifun.for iritec.for iridreg.for igrf.for cira.for iriflip.for \
 	--f77flags="-fPIC -O3 -w" --f90flags="-fPIC -O3 -w"
	mv iri_fcore*.so ../