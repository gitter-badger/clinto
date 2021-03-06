# clinto
This converts an assortment of python command line interfaces into a language agnostic build spec for usage in GUI creation.

Here's a basic usage:
```
from clinto import argparse_specs
specs = argparse_specs.ArgParseNodeBuilder(script_path='/home/chris/Devel/pythomics/pythomics/scripts/proteinInference.py', script_name='Protein Inference')
specs.get_script_description()
{'description': '\nThis script will annotate a tab delimited text file with peptides with\ncorresponding proteins present in an annotation file, and can also\nuse this annotation to include iBAQ measures.\n',
 'inputs': [{'group': 'optional arguments',
   'nodes': [{'choice_limit': None,
     'choices': None,
     'help': 'Threads to run',
     'model': 'IntegerField',
     'name': 'p',
     'param': '-p',
     'required': False,
     'type': 'text',
     'value': 1},
    {'choice_limit': '1',
     'choices': None,
     'help': 'The fasta file to match peptides against.',
     'model': 'FileField',
     'name': 'fasta',
     'param': '-f',
     'required': False,
     'type': 'file',
     'upload': True},

...

    {'choice_limit': None,
     'choices': None,
     'help': 'Where to save the file with motifs. Default: --out file with _motif suffix.',
     'model': 'CharField',
     'name': 'motif_out',
     'param': '--motif-out',
     'required': False,
     'type': 'text'}]},
  {'group': 'Protein Grouping Options',
   'nodes': [{'checked': False,
     'choice_limit': 0,
     'choices': None,
     'help': 'Only group proteins with unique peptides',
     'model': 'BooleanField',
     'name': 'unique_only',
     'param': '--unique-only',
     'required': False,
     'type': 'checkbox'},
    {'checked': False,
     'choice_limit': 0,
     'choices': None,
     'help': 'Write the position of the peptide matches.',
     'model': 'BooleanField',
     'name': 'position',
     'param': '--position',
     'required': False,
     'type': 'checkbox'},
    {'checked': False,
     'choice_limit': 0,
     'choices': None,
     'help': 'Treat peptides as case-sensitive (ie separate modified peptides)',
     'model': 'BooleanField',
     'name': 'case_sensitive',
     'param': '--case-sensitive',
     'required': False,
     'type': 'checkbox'}]}],
 'name': 'abc',
 'path': '/home/chris/Devel/pythomics/pythomics/scripts/proteinInference.py'}
```
