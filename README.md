# RFGLS
A Rapid Generalized Least Squares Model for a GWAS
RFGLS uses a generalized least-squares method to perform single-marker association analysis, in
datasets of nuclear families containing parents, twins, and/or adoptees. It is designed for families
of no greater than four members. When conducting association analysis with a large number of
markers, as in GWAS, RFGLS uses rapid feasible generalized least-squares, an approximation to
feasible generalized least-squares (FGLS) that considerably reduces computation time with minimal
bias in p-values, and with negligible loss in power.
The package includes four functions. Function gls.batch() actually conducts GWAS using the
rapid feasible generalized least-squares approximation, under which the residual variance-covariance
matrix is estimated once from a regression of the phenotype onto covariates only, and is subsequently
"plugged in" for use in all subsequent single-SNP analyses. Function fgls() is called by
gls.batch(), and conducts a single FGLS regression. It can be used to simultaneously estimate
fixed-effects regression coefficients and the residual covariance matrix. Function gls.batch.get()
is useful to restructure data, for use with fgls(). Function FSV.frompedi() creates familystructure
variables based upon available information in a pedigree file. Functions gls.batch()
and gls.batch.get() use these family-structure variables, which represent the type of family to
which each participant belongs and how s/he fits into that family.
