# MCQ generator
### README

## AWS EC2 Ubuntu Instance Setup for Streamlit Application

### Steps

1. **Login to AWS Console**:
   - [AWS Console](https://aws.amazon.com/console/)
   - Sign in with your AWS credentials.

2. **Search for EC2**:
   - Search "EC2" and select it.

3. **Launch an Instance**:
   - Click "Launch Instance"
   - Choose "Ubuntu Server 20.04 LTS"
   - Select an instance type (e.g., t2.micro)
   - Configure instance, add storage and tags as needed
   - Configure the security group (details below)

4. **Review and Launch**:
   - Click "Launch"
   - Choose or create a key pair for SSH access.

### Instance Configuration

1. **Connect to Your Instance**:
   - Use the key pair to SSH into your instance.

### Machine Update and Package Installation

```bash
sudo apt update
sudo apt-get update
sudo apt upgrade -y
sudo apt install git curl unzip tar make sudo vim wget -y
```

### Cloning Your Repository

Replace `"Your-repository"` with your GitHub repository URL:

```bash
git clone "Your-repository"
```

### Streamlit Application Deployment

```bash
sudo apt install python3-pip
pip3 install -r requirements.txt
python3 -m streamlit run StreamlitAPP.py
```

### Adding OpenAI API Key

1. **Create .env File**:
   ```bash
   touch .env
   ```

2. **Edit .env File**:
   ```bash
   vi .env
   # Press 'i' to insert text
   # Add: OPENAI_API_KEY=your-api-key
   # Press 'Esc', then type ':wq' to save and exit
   ```

### Configuring Security Groups

1. **Navigate to Security Groups**:
   - In the EC2 dashboard, select "Security Groups" under "Network & Security".

2. **Edit Inbound Rules**:
   - Select your security group.
   - Click "Edit Inbound Rules".
   - Add rule for port `8501`:
     - Type: Custom TCP Rule
     - Port Range: 8501
     - Source: Anywhere (0.0.0.0/0) or My IP

### Troubleshooting

- Ensure ports are open in your security group.
- Verify .env file format and content.
- Check Streamlit and other dependencies.

### References

- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
- [Streamlit Documentation](https://docs.streamlit.io/)
- [OpenAI API Documentation](https://beta.openai.com/docs/)

---

This guide covers the essential steps to deploy a Streamlit application on an AWS EC2 Ubuntu instance. For further assistance, refer to the provided documentation links.
