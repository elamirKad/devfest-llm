# GPU Model Selection and Configuration Instructions

1. **Select a Model**
   - Choose the desired AI model for the task.
   - We are using https://huggingface.co/TheBloke/MythoMax-L2-13B-GPTQ

2. **Choose a Server with the Appropriate GPU**
   - Select a server that has the necessary GPU specifications.
   - You can pick it up here https://cloud.vast.ai/create/

3. **Configure with Shell Script**
   - Set up the configuration using a shell script.
    ```if [ ! -d oobabooga_linux ]; then
    apt install build-essential unzip -y
    wget https://github.com/oobabooga/text-generation-webui/archive/refs/tags/snapshot-2023-11-19.zip
    unzip text-generation-webui-snapshot-2023-11-19.zip
    rm text-generation-webui-snapshot-2023-11-19.zip
    cd text-generation-webui-snapshot-2023-11-19
    sed -i '14s/--chat/--chat --share/' webui.py
    chmod +x start_linux.sh
    else    
        cd oobabooga_linux
    fi
    ```

4. **Initiate the oobabooga Download**
   - Begin the download process of oobabooga.

   4.1. **Configure CMD Flag for Online Access**
      - Set up the `--share` command flag to enable online Access through Gradio.
      - You can find it in an unzipped folder named CMD_FLAGS.txt

   4.2. **Launch oobabooga**
      - Start the oobabooga application with start_linux.sh.
      - You might need to give yourself permission to run it with chmod +x start_linux.sh
      - It will give you a public URL from Gradio at the end after setup. You can access it in the browser.

5. **Download the Model in oobabooga**
   - You would need to go into the Model tab in oobabooga, input the link from huggingface into the "Download model or LoRA" input, and click Download.

6. **Upload the Model in oobabooga**
   - After it is installed, you can click the restart button. After that, pick your established model and click Load.
   - Errors might occur. In that case, try to load the model a second time, as Oobabooga often changes its settings to match the model. If it doesn't help, try to debug it.

7. **Choose Operational Mode**
   - Begin working with the setup using Chat, Default, or Notebook tabs.

8. **Operate**
   - You can set up the character and model in parameters and start using it. Try to experiment with prompts; you can find examples on the internet.
