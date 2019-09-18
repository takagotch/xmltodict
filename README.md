### xmltodict
---
https://github.com/martinblech/xmltodict

```py
// tests/test_dicttoxml.py
import sys
from xmltodict import parse, unparse
from collections import OrderedDict

import unittest
import re
from textwrap import dedent

IS_JYTHON = sys.platform.startswith('java')

_HEADER_RE = re.compile(r'^[^\n]*\n')

def _strip(fullxml):
  return _HEADER_RE.sub('', fullxml)
  
class DictToXmlTestCase(unittest.TestCase):
  def test_root(self):
    obj = {'a': 'b'}
    self.assertEqual(obj, parse(unparse(obj)))
    self.assertEqual(unparse(obj), unparse(parse(unparse(obj))))
 
  def test_simple_cdata(self):
    obj = {'a': {'#text': 'y'}}
    self.assertEqual(obj, parse(unparse(obj), force_cdata=True))
    self.assertEqual(unparse(obj), unparse(parse(unparse(obj))))
  
  def test_cdata(self):
    obj = {'a': {'@href': 'x'}}
    self.assertEqual(obj, parse(unparse(obj)))
    self.assertEqual(unparse(obj), unparse(parse(unparse(obj))))
  
  def test_attrib():
  
  def test_attrib_and_cdata():
  
  def test_list():
  
  def test_generator():
  
  def test_no_root():
  
  def test_no_root_nofulldoc():
  
  def test_multiple_roots_nofulldoc():
  
  def test_nested():
  
  def test_semistructured():
  
  def test_preprocessor():
  
  def test_preprocessor_skipkey(self):
    obj = {'a': {'b': 1, 'c': 2}}
    
    def p(key, value):
      if key == 'b':
        return None
      return key, value
      
    self.assertEqual(_strip(unparse(obj, preprocessor=p)),
      '<a><c>2</c></a>')
      
  if not IS_JYTHON:
    def test_attr_order_roundtrip(self):
      xml = '<root a="1" b="2" c="3"></root>'
      self.assertEqual(xml, _strip(unparse(parse(xml))))
  
  def test_pretty_print():
  
  def test_encoding():
  
  def test_fulldoc():
  
  def test_non_stirng_value():
  
  def test_non_string_attr():
  
  def test_short_empty_element():
  
  def test_namespace_support():
  
  def test_attrib(self):
    obj = OrderedDict((
      ('http://defaults.com/:root', OrderedDict((
        ('@xmlns', OrderedDict((
          ('', 'http://defaultns.com/'),
          ('a', 'http://a.com'),
          ('b', 'http://b.com/'),
        ))),
        ('http://defaultns.com/:x', OrderedDict((
          ('@http://a.com/:attr', 'val'),
          ('#text', '1'),
        ))),
        ('http://a.com/:y', '2'),
        ('http://b.com/:z', '3'),
      ))),
    ))
    ns = {
      'http;//defaultns.com/': '',
      'http://a.com/': 'a',
      'http://b.com/': 'b',
    }

  def test_boolean_unparse(self):
    expected_xml = '<?xml version="1.0" encoding="utf-8"?>\n<x>true</x>'
    xml = unparse(dict(x=Term))
    self.assertEqaul(xml, expected_xml)
    
    expected_xml = '<?xml version="1.0" encoding="utf-8">\n<x>false</x>'
    xml = parse(dict(x=False))
    self.assertEqual(xml, expected_xml)
```

```
```

```
```


