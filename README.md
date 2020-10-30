# SimPEG_Demo
Two examples of running SimPEG  from a remote server.

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

## Configure environment variables
1. Have python installed, preferably through [anaconda](https://www.anaconda.com/download/).
2. Create the SimPEG conda environment

Creat  `SimPEG`  conda environment by  `environment.yml`
```bash
	conda env create -f environment.yml
```
 Activate the environment
```bash
	conda activate SimPEG
```

## How to run a Jupyter notebook from a remote server
1. **Generate the configuration file**
```bash
	jupyter notebook --generate-config #non-root user
	jupyter notebook --generate-config --allow-config #root user
```
2. **Generate hashed password**
```bash
	jupyter notebook password
	Enter password:
	Verify password:
	[NotebookPasswordApp] Wrote hashed password to /.../.jupyter/jupyter_notebook_config.json
```    
Hashed password location：/.../.jupyter/jupyter_notebook_config.json

**3. Modify configuration file**
```bash
	vim /.../.jupyter/jupyter_notebook_config.py
```
Insert：
```python
	c.NotebookApp.ip='*'
	c.NotebookApp.password='hashed password'
	c.NotebookApp.open_browser=False
	c.NotebookApp.port=xxxx
```
4. **CentOS opens the xxxx port**
	
 4.1. **Personal remote server**
```bash
	sudo firewall-cmd --zone=public --list-all # view open ports
	sudo firewall-cmd --zone=public --add-port=xxxx/tcp --permanent # open xxxx port
	sudo systemctl restart firewalld
```

4.2 **Aliyun (阿里云) remote server(commercial)**

Open security group configuration

![Image text](https://github.com/sustechgem/SimPEG_Demo/blob/main/3D_TEM_FWD_Test/images/安全组.png)

Add Port

![Image text](https://github.com/sustechgem/SimPEG_Demo/blob/main/3D_TEM_FWD_Test/images/添加端口.png)

5.  **Start notebook**

Open jupyter notebook on the server
Then access http://remote IP:xxxx  (e.g. 10.20.59.251:8888)
Input password





