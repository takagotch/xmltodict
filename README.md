### xmltodict
---
https://github.com/martinblech/xmltodict

```py
// tests/test_dicttoxml.py

def _strip(fullxml):
  return _HEADER_RE.sub('', fullxml)
  
class DictToXmlTestCase(unittest.TestCase):
  def test_root(self):
  
  def test_simple_cdata(self):
  
  def test_cdata(self):
  
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


