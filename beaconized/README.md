The files `genomicVariations*_json` are created using [beacon2-ri-tools-v2](https://github.com/EGA-archive/beacon2-ri-tools-v2?tab=readme-ov-file#converting-data-from-vcfgz-file).
To recreate the files, the following command needs to be run for every `.vcf.gz` file:
`docker exec -it ri-tools python genomicVariationsX_vcf.py`.
See [the documentation](https://github.com/EGA-archive/beacon2-ri-tools-v2?tab=readme-ov-file#converting-data-from-vcfgz-file) for more information.
Note that if you intend to beaconize several genomics file, you will have to empty the mongo DB between each of them:
`docker exec ri-tools-mongo /bin/bash -c 'mongo beacon -u root -p example --authenticationDatabase admin --eval "db.genomicVariations.deleteMany({})"'`

Instruction on how to generate the other files can be [found here](https://github.com/EGA-archive/beacon2-ri-tools-v2?tab=readme-ov-file#creating-the-csv-file-if-metadata-or-not-having-a-vcf-file-for-genomicvariations).
