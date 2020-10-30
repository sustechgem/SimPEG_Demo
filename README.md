# SimPEG_Demo
An examples of running SimPEG  from a remote server.

Learn more about SimPEG from [here](https://pypi.org/project/SimPEG/).
- SimPEG:0.14.2
## Notice 
Replace the `path` by your actual path in `3D_TEM_FWD_Test.ipynb`:
```=python
# load FDTD solutions (Sun et al., 2018)
data1 = pd.read_table('/.../3D_TEM_FWD_Test/data/50.dat', header=None)
data1 = np.array(data1)
data2 = pd.read_table('/.../3D_TEM_FWD_Test/data/150.dat', header=None)
data2 = np.array(data2)
data3 = pd.read_table('/.../3D_TEM_FWD_Test/data/450.dat', header=None)
data3 = np.array(data3)
data4 = pd.read_table('/...3D_TEM_FWD_Test/data/1050.dat', header=None)
data4 = np.array(data4)
```
