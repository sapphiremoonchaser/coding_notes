# Running Tests

### Run all Tests

`pytest`

looks for `tests/`, `test_*.py`, and `test_*` functions


### Run only one file

`pytest tests/models/test_filter.py`


### Verbose output

`pytest -v`


| Goal              | Command                           |
| ----------------- | --------------------------------- |
| Run all tests     | `pytest`                          |
| Run one file      | `pytest tests/.../test_pandas.py` |
| Run one function  | `pytest file.py::test_name`       |
| Run by name match | `pytest -k substring`             |
| Stop on failure   | `pytest -x`                       |
| Verbose           | `pytest -v`                       |
