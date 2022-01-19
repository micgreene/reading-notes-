# 10 Minutes to Pandas

**This is a short introduction to pandas, geared mainly for new users.**
+ Customarily, we import as follows:
  + `import numpy as np`
  + `import pandas as pd`

### Object creation

+ Creating a Series by passing a list of values, letting pandas create a default integer index:

`s = pd.Series([1, 3, 5, np.nan, 6, 8])`<br />
`print(s)`<br />
`{0: 1.0, 1: 3.0, 2: 5.0, 3: NaN, 4: 6.0, 5: 8.0}`<br />
`dtype: float64`<br />

+ Creating a DataFrame by passing a NumPy array, with a datetime index and labeled columns:

`dates = pd.date_range("20130101", periods=6)`<br />

`print(dates)`<br />
`DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04', '2013-01-05', '2013-01-06'],`<br />
`dtype='datetime64[ns]', freq='D')`<br />

`df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))`

+ ^ This will create a table of 4 rows headed by the input dates from the dates list we created above and 4 columns named 'ABCD' like we chose in the DataFrane() method.
Creating a DataFrame by passing a dict of objects that can be converted to series-like.

`df2 = pd.DataFrame({`<br />
          `"A": 1.0,`<br />
          `"B": pd.Timestamp("20130102"),`<br />
          `"C": pd.Series(1, index=list(range(4)), dtype="float32"),`<br />
          `"D": np.array([3] * 4, dtype="int32"),`<br />
          `"E": pd.Categorical(["test", "train", "test", "train"]),`<br />
          `"F": "foo",`<br />
     `})`<br />

+ The columns of the resulting DataFrame have different dtypes.

`df2.dtypes`<br />
 <br />
`A           float64`<br />
`B    datetime64[ns]`<br />
`C           float32`<br />
`D             int32`<br />
`E          category`<br />
`F            object`<br />
dtype: object
If you’re using IPython, tab completion for column names (as well as public attributes) is automatically enabled. Here’s a subset of the attributes that will be completed:

df2.<TAB>  # noqa: E225, E999
df2.A                  df2.bool
df2.abs                df2.boxplot
df2.add                df2.C
df2.add_prefix         df2.clip
df2.add_suffix         df2.columns
df2.align              df2.copy
df2.all                df2.count
df2.any                df2.combine
df2.append             df2.D
df2.apply              df2.describe
df2.applymap           df2.diff
df2.B                  df2.duplicated
As you can see, the columns A, B, C, and D are automatically tab completed. E and F are there as well; the rest of the attributes have been truncated for brevity.
  + Code Consoles provide transient scratchpads for running code interactively, with full support for rich output. A code console can be linked to a notebook kernel as a computation log from the notebook, for example.

  + Kernel-backed documents enable code in any text file (Markdown, Python, R, LaTeX, etc.) to be run interactively in any Jupyter kernel.

  + Notebook cell outputs can be mirrored into their own tab, side by side with the notebook, enabling simple dashboards with interactive controls backed by a kernel.

  + Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. For example, it is easy to have live preview of Markdown, Delimiter-separated Values, or Vega/Vega-Lite documents.

+ JupyterLab also offers a unified model for viewing and handling data formats. JupyterLab understands many file formats (images, CSV, JSON, Markdown, PDF, Vega, Vega-Lite, etc.) and can also display rich kernel output in these formats. 

+ To navigate the user interface, JupyterLab offers customizable keyboard shortcuts and the ability to use key maps from vim, emacs, and Sublime Text in the text editor.

+ JupyterLab extensions can customize or enhance any part of JupyterLab, including new themes, file editors, and custom components.

+ JupyterLab is served from the same server and uses the same notebook document format as the classic Jupyter Notebook.

## JupyterLab Releases¶
+ Since JupyterLab 0.32 (February 2018), the releases of JupyterLab are suitable for general daily use by both Jupyter novices and users experienced with the Classic Notebook interface. As of the 1.0 release (June 2019), it is additionally ready for extension writers who wish to further customize the JupyterLab experience for others.
