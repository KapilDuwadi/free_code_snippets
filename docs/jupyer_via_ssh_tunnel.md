

1. SSH into remote machine and activate proper python environment. Visit [here](ec2_instance.md) for instructions on how to SSH into EC2 instance in AWS.

2. Execute following command to run jupyter notebook on remote machine. Make sure to have jupyter intsalled in the python environment and feel free to change the port if necessary in remote server
    ```
    jupyter notebook --no-browser --port 1234
    ```
    You will see output similar to this.
    ```
    [I 21:41:44.813 NotebookApp] JupyterLab extension loaded from /home/ec2-user/anaconda3/lib/python3.7/site-packages/jupyterlab
    [I 21:41:44.813 NotebookApp] JupyterLab application directory is /home/ec2-user/anaconda3/share/jupyter/lab
    [I 21:41:44.815 NotebookApp] Serving notebooks from local directory: /home/ec2-user/nyserda/jupyter_plots
    [I 21:41:44.815 NotebookApp] The Jupyter Notebook is running at:
    [I 21:41:44.816 NotebookApp] http://localhost:1234/?token=7137121825535e9cfabc38ac45ad0e26f9aff7b131c95534
    [I 21:41:44.816 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
    [C 21:41:44.816 NotebookApp] 
    
    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://localhost:1234/?token=7137121825535e9cfabc38ac45ad0e26f9aff7b131c95534
    ```

3. Now open a command prompt from your local computer and execute following command. Note I am using Identity .pem file to authenticate myself to EC2 instance
   
   ```
   ssh -i credential.pem -NL 1234:localhost:1234 ec2-user@<ip-address>
   ```

4. Now open up your computer's browser and visit `localhost:1234`. Input the token obtained in step 2 and you are good to go.


5. If you get 500 Internal server error while opening a jupyter notebook. You may need to downgrade your tornado and nbconvert python module (https://github.com/scrapinghub/splash/issues/887)

    ```
    pip uninstall tornado
    pip uninstall nbconvert
    pip install nbconvert==5.3.1
    pip install tornado==4.2
    ```

