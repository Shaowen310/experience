# Python Argument



```python
import argparse
import json

def get_args():
    parser = argparse.ArgumentParser()
    
    parser.add_argument('--save_json',
        help='Save settings to file in json format. Ignored in json file')
    parser.add_argument('--load_json',
        help='Load settings from file in json format. Command line options override values in file.')
    
    args = parser.parse_args()
    
    if args.load_json:
        with open(args.load_json, 'rt') as f:
            t_args = argparse.Namespace()
            t_args.__dict__.update(json.load(f))
            args = parser.parse_args(namespace=t_args)
    
    # Optional: support for saving settings into a json file
    if args.save_json:
        with open(args.save_json, 'wt') as f:
            json.dump(vars(args), f)
            
    return args
```

\
