# Curriculum Vitae

## 1. Name and surname
**Name:** Maxim

**Surname:** Yudenkov

## 2. Contacts for communication
**Phone:** +375336772262

**E-mail:** fargotus@mail.ru

**Social networks:**

* *Telegram:* @IsadoraDuncan1737
* *VK:* @bestctulhuever
* *GitHub:* IsadoraDuncan1737
* *Discord:* IsadoraDuncan1737#6742

## 3. About Me
I am a student of the Belarusian-Russian University, studying in the third year of the specialty "Software Engineering". I'm sociable, smart, patient and creative. During my studies, I want to improve my programming skills and learn new programming technologies. After graduation I want to get a job in some IT company to further develop my skills in the field of programming.

## 4. Skills
* **Programming languages:**
    + Java (basics)
    + C# (basics)
    + Javascript (basics)
* **Frameworks:**
    + .NET
    + ASP.NET (basics)
* **Software development methodologies:**
    + Agile
* **Version control systems:**
    + Git

## 5. Code samples
* **Render function for adding welding sample**

```
    renderContestSampleForm() {
        return (
            <Form>
                <fieldset disabled={true}>
                    <Row>
                        <Col>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">Форма</Form.Label>
                                <Form.Control size="sm" type="text"
                                    placeholder={this.state.currentContestSample.shape} />
                            </Form.Group>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">Толщина</Form.Label>
                                <Form.Control size="sm" type="number"
                                    placeholder={this.state.currentContestSample.thickness} />
                            </Form.Group>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">Материал</Form.Label>
                                <Form.Control size="sm" type="text"
                                    placeholder={this.state.currentContestSample.material} />
                            </Form.Group>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">Диаметр</Form.Label>
                                <Form.Control size="sm" type="number"
                                    placeholder={this.state.currentContestSample.diameter} />
                            </Form.Group>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">Ссылка на паспорт заготовки</Form.Label>
                                <Form.Control size="sm" type="text"
                                    placeholder={this.state.currentContestSample.passportLink} />
                            </Form.Group>
                        </Col>
                        <Col>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">RFID</Form.Label>
                                <Form.Control size="sm" type="text"
                                    placeholder={this.state.currentContestSample.rfid} />
                            </Form.Group>
                            <Form.Group className="mb-3">
                                <Form.Label size="sm">QR</Form.Label>
                                <Form.Control size="sm" type="text"
                                    placeholder={this.state.currentContestSample.qr} />
                            </Form.Group>
                        </Col>
                    </Row>
                </fieldset>
            </Form>
        );
    }
```

* **Component for multiple file uploads from the client**
     
```
export class AddFileMultipleComponent extends Component {
    static displayName = AddFileMultipleComponent.name;

    constructor(props) {
        super(props);

        this.state = {
            uploadedFiles: [],
            fileLimit: false,
            maxFilesCount: 10,
        }

        this.handleFileEvent = this.handleFileEvent.bind(this);
        this.handleUploadFiles = this.handleUploadFiles.bind(this);
    }

    handleUploadFiles(files) {
        const uploaded = [...this.state.uploadedFiles];
        let limitExceeded = false;
        files.some((file) => {
            if (uploaded.findIndex((f) => f.name === file.name) === -1) {
                uploaded.push(file);
                if (uploaded.length === this.state.maxFilesCount) {
                    this.setState({ fileLimit: true });
                }

                if (uploaded.length > this.state.maxFilesCount) {
                    alert(`Вы не можете добавить больше ${this.state.maxFilesCount} файлов`);
                    this.setState({ fileLimit: false });
                    limitExceeded = true;
                    return true;
                }
            }
        });

        if (!limitExceeded) {
            this.setState({ uploadedFiles: uploaded });
            this.props.handleChangeFiles(uploaded);
        }
    }

    handleFileEvent(e) {
        const chosenFiles = Array.prototype.slice.call(e.target.files);

        this.handleUploadFiles(chosenFiles);
    }

    render() {
        if (!this.props.isHidden) {
            return (
                <div className="AddFileMultiple">

                    <input id='fileUpload' type='file' multiple hidden={true}
                        accept='image/png, image/jpeg, image/jpg'
                        onChange={(e) => { this.handleFileEvent(e) }}
                        disabled={this.state.fileLimit}
                    />

                    <label htmlFor='fileUpload' >
                        <a className={`btn btn-primary ${!this.state.fileLimit ? '' : 'disabled'} `}>
                            Выбрать файлы
                        </a>
                    </label>
                </div>
            )
        }
    }
}
```

## 6. Work experience

I am working on a project to automate a welding competition, but since this is a private order, I cannot share it :p

[Link to repository with Curriculum Vitae](https://github.com/IsadoraDuncan1737/SVChsVC_Yudenkov_PIR-201.github.io)

## 7. Courses and trainings

I tried to pass the training from epam, but failed at the first stage :P

## 8. English level

A2 Elementary

## 9. Photo or avatar

![If you don't see any image, then I failed at some stage](avatar.jpg)