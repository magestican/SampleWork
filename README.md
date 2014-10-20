SampleWork
==========

This repository contains samples of my code



Sample Code of an angularJS implementation

--Some Page--
==========

	 <div class="credentials-page wrapper-content" ng-controller="CredentialsController">
    	<h2 class="page-subheader">3. CREDENTIALS</h2>
    	<p>
        Please provide license numbers and expiration dates for the required licenses below. If your licenses do not show two years of experience,
        please also upload documents providing proof of two years of experience such as financial statement or letters of reference for similar work
        experience.
	 </p>

    <!--1-->
    <div ng-show="model2.companytype == 'Contractor' && model2.program.acqc">

        <text:box subtitle width="100%" titletext="Required License for ACQC"></text:box>

        <text:box label titletext="Licenses Type" text="C-20"></text:box>

        <text:box validme validmefor="text" validmeaction="global.save" titletext="Licenses Number" required modelbind="model.licenseNumber1"></text:box>

        <text:box validme validmefor="text" validmeaction="global.save" titletext="Expiration Date" width="60%" modelbind="model.expirationDate1"></text:box>


        <text:box validme validmefor="text" validmeaction="global.save" leftlabel width="602px" options="License shows at least 2 years in business @ License does not show two years in business, but I can submit other documents to show experience" titletext="Experience" modelbind="model.experience1" subtext="(select one)"></text:box>

    </div>


    <!--extra1-->
    <div ng-if="(model2.companytype == 'Contractor' && model2.program.acqc)  && model.experience1 == 'License does not show two years in business, but I can submit other documents to show experience'">
        <text:box subtitle width="100%" titletext="Select one option below:"></text:box>

        <div id="optionA1" class="doublecontainer">
            <input type="radio" name="radioLicenseProof" ng-init="model.licenseProof = true" ng-model="model.licenseProof" class="spanlike text-box-radio" value="1" >
            <div class="container spanlike">
                <text:box nobold subtitle width="100%" titletext="Provide financial records and professional references as proof"></text:box>

                <text:box nobold subtitle width="100%" titletext="Upload financial records dating back two years that provide proof of at least two years in business"></text:box>

                <upload:button width="92%" hint="You can provide utility bills, bank statements, or other financial records." titletext="" modelbind="model.financialrecordsproof2">  </upload:button>

                <text:box nobold subtitle width="100%" titletext="AND Upload two written professional references from a colleague or previous employer testifying to your work experience relating to this license type"></text:box>

                <text:box nobold subtitle width="100%" titletext="Professional Reference 1"></text:box>
                <upload:button width="92%" titletext="" modelbind="model.professionalreferenceB1">  </upload:button>

                <text:box nobold subtitle width="100%" titletext="Professional Reference 2"></text:box>
                <upload:button width="92%" titletext="" modelbind="model.professionalreferenceB2">  </upload:button>

            </div>
        </div>


        <text:box nobold subtitle width="100%" titletext="OR"></text:box>

        <div id="optionA2" class="doublecontainer">
            <input type="radio" name="radioLicenseProof" class="spanlike text-box-radio" ng-model="model.licenseProof" value="2">
            <div class="spanlike container ">
                <text:box nobold subtitle width="100%" titletext="Provide BPI accreditation certificate"></text:box>
                <upload:button width="92%" titletext="" modelbind="model.bpiaccreditationcertificate2">  </upload:button>

            </div>
        </div>
    </div>
    <!--2-->
    <div ng-show="model2.companytype == 'Contractor' && ( model2.program.ahu || (model2.program.ahu && program.hu))">

        <text:box subtitle width="100%" titletext="Required License for Advanced Home Upgrade"></text:box>

        <text:box label titletext="Licenses Type" text="B License"></text:box>

        <text:box titletext="Licenses Number" required modelbind="model.licenseNumber2"></text:box>

        <text:box titletext="Expiration Date" width="60%" modelbind="model.expirationDate2"></text:box>

        <text:box leftlabel width="602px" options="License shows at least 2 years in business @ License does not show two years in business, but I can submit other documents to show experience" titletext="Experience" modelbind="model.experience2" subtext="(select one)"></text:box>

    </div>
    <!--3-->
    <div ng-show="model2.companytype == 'Contractor' && (model2.program.hu && (!model2.program.ahu && !model2.program.acqc))">

        <text:box subtitle width="100%" titletext="Required License for Home Upgrade"></text:box>

        <text:box leftlabel titletext="Licenses Type" modelbind="model.licensetype" selectoptions="- Select -@B@C-2@C-4@C-5@C-6@C-7@C-8@C-9@C-10@C-11@C-12@C-13@C-14@C-15@C-16@C-20@C-23@C-28@C-29@C-31@C-32@C-33@C-34@C-35@C-36@C-39@C-42@C-43@C-45@C-46@C-47@C-50@C-51@C-53@C-54@C-55@C-57@C-60@HAX@HIC"></text:box>

        <text:box titletext="Licenses Number" required modelbind="model.licenseNumber3"></text:box>

        <text:box titletext="Expiration Date" width="60%" modelbind="model.expirationDate3"></text:box>

        <text:box leftlabel width="602px" options="License shows at least 2 years in business @ License does not show two years in business, but I can submit other documents to show experience" titletext="Experience" modelbind="model.experience3" subtext="(select one)"></text:box>

    </div>
    <!--4-->
    <div ng-show="model2.companytype == 'Individual Rater'">

        <text:box subtitle width="100%" titletext="BPI Professional info"></text:box>

        <text:box leftlabel titletext="Type of BPI Certification" modelbind="model.licensetype2" selectoptions="- Select -@Advanced Home Energy Professional(HEP) Certification @ Air Conditioning and Heat Pump @ Building Analyst @ Envelope Professional @ Heating @ Residential Building Envelope Whole House Air Leakage Controller Installer"></text:box>

        <upload:button width="58%" modelbind="model.bpicard" titletext="Upload a Copy of BPI Card"></upload:button>

        <text:box subtitle width="100%" titletext="HERS Whole House Rater Certification"></text:box>

        <upload:button width="58%" modelbind="model.hers2card" titletext="Upload a Copy of HERS ID Card"></upload:button>

    </div>
    <!--5-->
    <div ng-show="model2.companytype == 'Rater Company'">

        <text:box label titletext="Accreditation Type" text="BPI"></text:box>

        <upload:button width="58%" modelbind="model.bpicard" titletext="Copy of BPI Accreditation" filesize="10MB or less" typeoffile="PDF"></upload:button>

    </div>

    <!--extra2-->
    <div ng-if="model.experience3 == 'License does not show two years in business, but I can submit other documents to show experience' || model.experience2 == 'License does not show two years in business, but I can submit other documents to show experience'">
        <text:box subtitle width="100%" titletext="Select one option below:"></text:box>

        <div id="optionB1" class="doublecontainer">
            <input type="radio" name="radioLicenseProof2" ng-init="model.licenseProof2 = true" ng-model="model.licenseProof2" class="spanlike text-box-radio" value="1">
            <div class="container spanlike">
                <text:box nobold subtitle width="100%" titletext="Provide financial records and professional references as proof"></text:box>

                <text:box nobold subtitle width="100%" titletext="Upload financial records dating back two years that provide proof of at least two years in business"></text:box>

                <upload:button width="92%" hint="You can provide utility bills, bank statements, or other financial records." titletext="" modelbind="model.financialrecordsproof">  </upload:button>

                <text:box nobold subtitle width="100%" titletext="AND Upload two written professional references from a colleague or previous employer testifying to your work experience relating to this license type"></text:box>

                <text:box nobold subtitle width="100%" titletext="Professional Reference 1"></text:box>
                <upload:button width="92%" titletext="" modelbind="model.professionalreferenceA1">  </upload:button>

                <text:box nobold subtitle width="100%" titletext="Professional Reference 2"></text:box>
                <upload:button width="92%" titletext="" modelbind="model.professionalreferenceA2">  </upload:button>

            </div>
        </div>


        <text:box nobold subtitle width="100%" titletext="OR"></text:box>

        <div id="optionB2" class="doublecontainer">
            <input type="radio" name="radioLicenseProof2" class="spanlike text-box-radio" ng-model="model.licenseProof" value="2">
            <div class="spanlike container ">
                <text:box nobold subtitle width="100%" titletext="Provide BPI accreditation certificate"></text:box>
                <upload:button width="92%" titletext="" modelbind="model.bpiaccreditationcertificate">  </upload:button>

            </div>
        </div>
    </div>

</div>


--Directives Used--
==========

	angular.module('Directives')
        .directive('textBox', ['$filter', '$rootScope', 'fileUploader', '$compile', 'Helper', function ($filter, $rootScope, 		fileUploader, $compile, Helper) {
            return {
                restrict: 'E',
                scope: true,
                link: function (scope, element, attrs, controllers) {
                    scope.model = $rootScope.global.currentControllerModel;
                    var render = function () {
                        //beginning tag
                        var template = '<div  ' + (attrs.showcondition != undefined ? "ng-show = \"" + attrs.showcondition + "  \"" : "") + ' ' + (attrs.height != undefined ? "style=\"height: " + attrs.height + "\" " : "") + '  class="pdll form-horizontal">';
                        if (attrs.subtitle != undefined) {
                            template += '<div class="row"><div class="col-sm-3 mrmb subtitle ' + (attrs.nobold != undefined ? "nobold" : "") + ' "  ' + (attrs.width != undefined ? "style = \"width:" + attrs.width + "  \"" : "") + '>' + attrs.titletext + '</div><a class="col-sm-5 edit-lnk " ng-hide="editMode" ng-click="editMode=true">Edit</a></div>'
                        } else if (attrs.leftlabel != undefined) {
                            if (attrs.titletext != undefined && attrs.titletext != "") {
                                template += '<div class="form-group"> <div class="control-label col-sm-3"><div> <label >' + attrs.titletext + '</label></div>   <div> <label class=" italica control-label">' + (attrs.subtext != undefined ? attrs.subtext : "") + '</label>  </div> </div>';
                            }
                            template = attrs.selectoptions != undefined ? scope.addSelectItems(template) : scope.addRadioButtons(template);
                            if (attrs.titletext != undefined && attrs.titletext != "") {
                                template += '</div>';
                            }
                        } else {
                            template += '<div class="form-group"> <label class="col-sm-3 control-label">' + attrs.titletext + '</label><div class="col-sm-5">';
                            if (attrs.label == undefined) {
                                template += '<input  ' +
                                    (attrs.width != undefined ? "style = \"width:" + attrs.width + "  \"" : "") +
                                    (attrs.validme != undefined ? "validme='" + attrs.validme + "'" : "") +
                                    (attrs.validmeaction != undefined ? "validmeaction='" + attrs.validmeaction + "'" : "") +
                                    (attrs.validmefor != undefined ? "validmefor='" + attrs.validmefor + "'" : "") +
                                    'type="' + attrs.type + '" value="' + attrs.text + '" class="form-control"   ng-model="' + attrs.modelbind + '" ' +
                                    (attrs.isrequired != undefined ? "required" : "") + ' ></div></div>';
                            } else {
                                template += '<label  style="text-align:left"  class="control-label bold " >' + attrs.text + '</label></div></div>';
                            }
                        }
                        //end tag
                        template += '</div>';

                        unescape(template);

                        element.html(template);
                        var e = $compile(template, { transclude: true })(scope);
                        element.replaceWith(e);

                    }
                    scope.addRadioButtons = function (template) {

                        if (attrs.options != undefined) {
                            var uploadoptions = [];
                            
                            if (attrs.uploadoptions)
                                uploadoptions = attrs.uploadoptions.split('@');
                            angular.forEach(attrs.options.split('@'), function (option, index) {

                                template += '<label class="col-sm-5 ' + (attrs.class != undefined ? attrs.class : "") + '\" ' + (attrs.width != undefined ? "style = \"width:" + attrs.width + "  \"" : "") + '   ><input type="radio" ' +
                                    (attrs.validme != undefined ? "validme='" + attrs.validme + "'" : "") +
                                    (attrs.validmeaction != undefined ? "validmeaction='" + attrs.validmeaction + "'" : "") +
                                    (attrs.validmefor != undefined ? "validmefor='" + attrs.validmefor + "'" : "") +
                                    'name="inlineRadioOptions' + attrs.modelbind.split(".")[1] + '"  value="' + option + '" ng-model="' + attrs.modelbind + '"  ' + (index == 0 ? "checked"  : "") + '> ' +
                                    (attrs.optiontitles != undefined ? '<span class="bold"> ' + attrs.optiontitles.split('@')[index].trim() + ': </span>' : "") +
                                    option + ' </label>' +
                                    (attrs.uploadoptions && uploadoptions[index] ? "<upload:button titletext=\"\" width=\"80%\" class=\"mrlt\"  modelbind=\"" + uploadoptions[index] + "\"></upload:button>" : "")

                                ;

                            })
                        }
                        return template;
                    }
                    scope.addSelectItems = function (template) {

                        if (attrs.selectoptions != undefined) {
                            scope.selectoptions = [];

                            angular.forEach(attrs.selectoptions.split('@'), function (option) {
                                scope.selectoptions.push(option);
                            })
                            //set default value as first value
                            scope.model[attrs.modelbind.split('.')[1]] = scope.selectoptions[0];
                            template += '<select ng-model="' + attrs.modelbind + '" ' +
                                (attrs.validmeaction != undefined ? "validmeaction='" + attrs.validmeaction + "'" : "") +
                                (attrs.validme != undefined ? "validme='" + attrs.validme + "'" : "") +
                                (attrs.validmeaction != undefined ? "validmeaction='" + attrs.validmeaction + "'" : "") +
                                (attrs.validmefor != undefined ? "validmefor='" + attrs.validmefor + "'" : "") +
                                'ng-options="option for option in  selectoptions" style="padding: 5px;margin-left: 15px;" class="mrst txt-size-m spanlike table-offset">'
                        }
                        else {
                            console.log("Select options not specified for a select type textbox");
                        }
                        return template;
                    }


                    //rendering
                    if (attrs.modelbind != undefined || attrs.label != undefined || attrs.leftlabel != undefined || attrs.radio != undefined || attrs.subtitle != undefined) {
                        if (!attrs.text || attrs.text == '') {
                            attrs.text = "";
                        }
                        if (!attrs.type || attrs.type == '') {
                            attrs.type = "text";
                        }
                        if (attrs.selectoptions != undefined) {
                            if (attrs.modelbind == undefined) {
                                throw RegExp('Model bind not specified for a selectoption textbox')
                            }
                        }
                        if (attrs.modelbind != undefined) {
                            if (attrs.modelbind.indexOf('model') == -1) {
                                throw RegExp('You must specify the model word at the beggining of your bindable property');
                            }
                        }
                        render();
                    } else {
                        console.log("The specified textbox doesnt have the modelbind attribute");
                    }
                }
            };
        }]);


--And--
==========


	angular.module('Directives')
        .directive('uploadButton', ['$filter', '$rootScope', '$upload', 'fileUploader', '$compile', 'Helper', function 			($filter, $rootScope, $upload, fileUploader, $compile, Helper) {
            return {
                restrict: 'E',
                scope: true,
                link: function (scope, element, attrs, controllers) {
                    scope.model = $rootScope.global.currentControllerModel;
                    scope.setFileEventListener = function ($files) {
                        var reader = new FileReader();
                        scope.uploadedFile = $files[0];
                        reader.readAsDataURL(scope.uploadedFile);
                        reader.onload = function (imgsrc) {
                            if (checkValidFileTypes(scope.uploadedFile.name)) {
                                var toDelete = false;
                                //THIS IS TO KNOW IF WE HAVE TO DELETE THE COPY OF A FILE WITH THIS NAME ON THE SERVER
                                if (scope.model[attrs.modelbind.split('.')[1]] && scope.model[attrs.modelbind.split('.')[1]].name == scope.uploadedFile.name) {
                                    toDelete = true;
                                }
                                
                                scope.model[attrs.modelbind.split('.')[1]] = imgsrc;
                                if (toDelete)
                                    scope.model[attrs.modelbind.split('.')[1]].toDelete = true;
                                scope.model[attrs.modelbind.split('.')[1]].name = scope.uploadedFile.name;
                                scope.$apply();
                            }
                            else {
                                return;
                            }
                        }

                    }


                    scope.uploadFile = function () {
                        uploadFile();
                    };


                    function uploadFile() {
                        if (!scope.uploadedFile) {
                            return;
                        }

                        fileUploader.uploadFile_init($scope.uploadedFile)
                            .then(function (result) {
                                if (result.status == 200) {
                                    console.log('File uploaded successfully');
                                }
                            }, function (error) {
                                alert(error.message);
                            });
                    }


                    var checkValidFileTypes = function (fileName) {

                        var filearray = fileName.split('.');
                        if (filearray.length > 1) {
                            var extension = filearray[1];

                            var fileTypes = attrs.typeoffile.split(',')

                            var found = false;
                            angular.forEach(fileTypes, function (val) {
                                if (val.trim().toLowerCase() == extension)
                                    found = true;
                            })
                            return found;
                        }
                        else {
                            throw RegExp('Invalid file with no extension was submited');
                        }
                    }

                    var render = function () {
                        scope.alignToRight = (attrs.titletext == undefined || attrs.titletext == "")
                        scope.alignToBottom = !scope.alignToRight;

                        var template = '<div class="form-group form-horizontal "><label class="col-sm-3 control-label"  ' + (attrs.titletext == undefined || attrs.titletext == "" ? "style = \"width:0px\"" : "") + ' >' + attrs.titletext + '</label><div class="col-sm-5 mrml  ' + (attrs.class != undefined ? attrs.class : "") + '" ' + (attrs.width ? "style = \"width:" + attrs.width + "  \"" : "") + '><div><div   ng-file-select="setFileEventListener($files)"  class="upload-button hand spanlike" ><p><span class="pdml bold ha">' + attrs.text + '</span></p></div><input style="visibility:hidden;  width:0px"  id="hiddenUploadButton" type="file" class="spanlike form-control "><input disabled style="width:178px" type="text"   placeholder="No file selected" ng-model="model.' + attrs.modelbind.split('.')[1] + '.name" class=" spanlike mrll form-control "><div  style=\"' + (attrs.hintwidth != undefined ? "width:" + attrs.hintwidth + ";" : "") + '\"  ng-class="{\'right-label-upload-button  txt-size-m\' : alignToRight , \'italica txt-size-m\' : alignToBottom } ">  ' + (attrs.hint ? "<span style=\"color:gray;   \" class=\"bold\">" + (attrs.hinttitle ? attrs.hinttitle : "Hint") + ":</span>" : "") + (attrs.hint ? attrs.hint : "") + ' ' + attrs.typeoffile + ',' + attrs.filesize + '</div></div>    </div></div>';

                        element.html(template);
                        var e = $compile(template, { transclude: true })(scope);
                        element.replaceWith(e);
                    }
                    if (attrs.modelbind != undefined) {

                        if (attrs.modelbind.indexOf('model') == -1) {
                            throw RegExp('You must include the model word for the modelbind property in the uploadbutton directive')
                        }
                        if (!attrs.text || attrs.text == '') {
                            attrs.text = "Upload File";
                        }
                        if (!attrs.typeoffile || attrs.typeoffile == '') {
                            attrs.typeoffile = 'PDF, JPG, GIF, TIFF';
                        }
                        if (!attrs.filesize || attrs.filesize) {
                            attrs.filesize = '5MB or less';
                        }
                        render();
                    }
                }
            };
        }]);
		
		
-- And --
==========


	angular.module('Directives')
	 .directive('validme', ['$filter', '$compile', '$document', function ($filter, $compile, $document) {
        return {
            restrict: 'A',
            transclude: false,
            replace: true,
            scope: false,
            controller: function ($scope) {
                $scope.errorTemplate = '<div class="col-sm-5 errorLabel" style="width:70% !important"><label style="text-align:left" ng- class="control-label bold " ng-cloak>{{errorMessage}}</label></div>';
            },


            link: function (scope, element, attrs, controllers) {

                //dont do anything if the element wasnt compiled yet
                if (element[0].localName == "text:box")
                    return;
                if (element[0].localName == "text-box")
                    return;
                if (element[0].localName == "upload:button")
                    return;
                if (element[0].localName == "upload-button")
                    return;

                scope.global.validMeQueue = scope.global.validMeQueue == undefined ? [] : scope.global.validMeQueue;

                var index = scope.global.validMeQueue.length;
                //add this validation item to the global queue
                scope.global.validMeQueue.push(function validMeQueue(element) {


                    var result = { message: "", element: {}, good: true }
                    if (attrs.validmefor != undefined && attrs.validmefor != "") {
                        var value = element.val();
                        var ruleArray = attrs.validmefor.replace(" ", "").split("@");
                        var validRules = { type: "", rule: "" };
                        if (validRules.length > 1) {
                            validRules.type = ruleArray[0];
                            validRules.rule = ruleArray[1];
                        } else {
                            validRules.type = ruleArray[0];
                        }

                        if (validRules.type == "text") {
                            if (validRules.rule != undefined && (validRules.rule == "" || validRules.rule == "alphanumeric")) {
                                if (value != "") {
                                    result.good = true;
                                    return result;
                                }
                                else {
                                    result.good = false;
                                    result.message = "This field cannot be empty";
                                    return result;
                                }
                            }
                            else if (validRules.rule == "numeric") {
                                var part1 = "^[";
                                var part2 = "]+$";
                                var regex = new RegExp(part1 + "0-9" + part2);
                                if (regex.test(value)) {
                                    result.message = "Value " + value + " is numeric";
                                    console.log(result.message);
                                    result.good = true;
                                    return result;
                                } else {
                                    result.message = "This field should contain only numbers";
                                    result.good = false;
                                    return result;
                                }
                            }
                        }
                        if (validRules.type == "number") {
                            if (validRules.rule != undefined && validRules.rule != "") {
                                var part1 = "^[";
                                var part2 = "]+$";
                                var regex = new RegExp(part1 + validRules.rule + part2);
                                if (regex.test(value)) {
                                    result.message = "Value " + value + " is a number";
                                    console.log(result.message);
                                    result.good = true;
                                    return result;
                                } else {
                                    result.message = "This field should contain only numbers";
                                    result.good = false;
                                    return result;
                                }
                            }
                            else {
                                throw RegExp("You specified a number validation but didnt provide which set of numbers to validate");
                            }
                        }
                        if (validRules.type == "email") {
                            var re = /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
                            if (re.test(value)) {
                                result.message = "Value " + value + " is an email";
                                console.log(result.message);
                                result.good = true;
                                return result;
                            } else {
                                result.good = false;
                                result.message = "You should input a valid email";
                                return result;
                            }

                        }
                        if (validRules.type == "required") {
                            if (value == "") {
                                result.message = "This field is Required";
                                result.good = false;
                                console.log(result.message);
                                return result;
                            } else {
                                result.good = true;
                                return result;
                            }
                        }
                        //just in case
                        return result;
                    } else {
                        throw RegExp("You defined the valid-me attribute in an element but didnt define the \n " +
                            "valid-me-for attribute. Some valid values for it are  \n " +
                            "text \n" +
                            "text @ letters \n" +
                            "text @ alphanumeric \n" +
                            "number \n" +
                            "number @ 1-9 \n" +
                            "number @ 1-9 \n" +
                            "email \n" +
                            "required \n)")
                    }
                })
                //inject element into function
                scope.global.validMeQueue[index].element = element;

                angular.forEach(attrs.validmeaction.split('@'), function (validMeAction) {

                    //do not create the same unbiding/validation-triggering function twice
                    if (scope['turnOf' + validMeAction.replace('.', '')] == undefined) {

                        scope['turnOf' + validMeAction.replace('.', '')] = scope.$on(validMeAction, function (event) {

                            var lastErroredElement = {};
                            //execute queue
                            angular.forEach(scope.global.validMeQueue, function (validMeTask, index) {

                                validationTask(validMeTask);
                            })
                        });

                        //**CODE INJECTION PROCESS**//
                        var members = "scope";
                        angular.forEach(validMeAction.split('.'), function (member) {
                            members += '["' + member + '"]';
                        })
                        //wrap function to inject emit at the previous to function execution
                        var watchingFunction = eval(members);
                        function functionWrapper() {
                            that = functionWrapper;
                            //execute validation before anything else
                            scope.$emit(validMeAction);
                            try {
                                return that.watchingFunction.apply(this, arguments);
                            } catch (e) {
                                console.log("An error ocurred in " + that.watchingFunction.toString() + "\n \n . The particularity of the error is : \n" + e.message)
                                if (handle) {
                                    return handle(e);
                                }
                                else {
                                    console.log("error handling exception");
                                }
                            }
                        };
                        //set the watching function for nesting purposes
                        functionWrapper.watchingFunction = watchingFunction;
                        eval(members + " =  functionWrapper");
                    }
                })
                //ugly jquery like stuff
                var validationTask = function (validMeTask) {
                    var that = this;
                    var result = validMeTask(validMeTask.element);

                    if (!result.good) {
                        validMeTask.element.toggleClass('error-border', true);
                        //change left label (if exists) to have a red color
                        var possibleLabel = validMeTask.element.parent().parent().find("label:first-child");
                        if (possibleLabel.length > 0) {
                            possibleLabel.toggleClass('error-color', true);;
                        }
                        $document.scrollToElementAnimated(validMeTask.element, 80);


                        scope.errorMessage = result.message;
                        //do not append again
                        if (validMeTask.element.parent().find(".errorLabel").length == 0) {
                            var errorTemplate = angular.element(scope.errorTemplate);
                            $compile(errorTemplate)(scope);
                            validMeTask.element.parent().append(errorTemplate);
                        }
                        scope.$apply();
                    } else {
                        validMeTask.element.toggleClass('error-border', false);
                        validMeTask.element.parent().find(".errorLabel").remove();
                        var possibleLabel = validMeTask.element.parent().parent().find("label:first-child");
                        if (possibleLabel.length > 0) {
                            possibleLabel.toggleClass('error-color', false);;
                        }
                    }
                }
                //pre-emptive checkings
                element.bind('blur', function () {
                    validationTask(scope.global.validMeQueue[index]);
                });
            }
        };
    }]);
