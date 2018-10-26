<template>
<div class="control-section">
    <div class="progress-button-section">
        <div id="progress-button-control">
            <div class="row" class="check">
                <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6 margin">
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Spin Left" :isPrimary="true"></ejs-progressbutton>
                    </div>
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Spin Right" :isPrimary="true" :spinSettings="spinRight"></ejs-progressbutton>
                    </div>
                </div>
                <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6 margin">
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Spin Top" :isPrimary="true" :spinSettings="spinTop"></ejs-progressbutton>
                    </div>
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Spin Bottom" :isPrimary="true" :spinSettings="spinBottom"></ejs-progressbutton>
                    </div>
                </div>
            
                <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6 margin">
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton id="roundbtn" :spinSettings="spinCenter" :animationSettings="zoomOut" cssClass="e-round e-small e-success"
                            iconCss="e-icons e-play-icon"></ejs-progressbutton>
                    </div>
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton id="contract" ref="contractBtn" content="Contract" :enableProgress="true" cssClass="e-success e-small" :begin="contractBegin"
                            :end="contractEnd"></ejs-progressbutton>
                    </div>
                </div>
                <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6 margin">
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Slide Left" :enableProgress="true" :spinSettings="spinCenter" :animationSettings="slideLeft"
                            cssClass="e-flat e-success"></ejs-progressbutton>
                    </div>
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Slide Right" :enableProgress="true" :spinSettings="spinCenter" :animationSettings="slideRight"
                            cssClass="e-outline e-success"></ejs-progressbutton>
                    </div>
                </div>
          
                <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6 margin">
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton id="zoomin" content="Zoom In" :enableProgress="true" :spinSettings="spinCenter" :animationSettings="zoomIn"
                            cssClass="e-round-corner e-danger"></ejs-progressbutton>
                    </div>
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Zoom Out" :enableProgress="true" :spinSettings="spinCenter" :animationSettings="zoomOut"
                            cssClass="e-small e-danger"></ejs-progressbutton>
                    </div>
                </div>
                <div class="col-xs-6 col-sm-6 col-lg-6 col-md-6 margin">
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Download" :enableProgress="true" duration=4000 cssClass="e-hide-spinner e-progress-top"
                            iconCss="e-icons e-download-icon"></ejs-progressbutton>
                    </div>
                    <div class="col-xs-12 col-sm-12 col-lg-6 col-md-6">
                        <ejs-progressbutton content="Disabled" :disabled="true"></ejs-progressbutton>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<style>
#progress-button-control {
    width: 100%;
    margin: 8% 0;
    text-align: center;
}

@media only screen and (max-width: 500px) {
    #progress-button-control {
        margin-left: -11%;
    }
}

.progress-button-section {
    width: 80%;
    margin: auto;
}

#progress-button-control .col-xs-12 {
    margin: 18px 0;
}

#contract.e-progress-active .e-btn-content {
    display: none;
}

#contract {
    transition: all .3s cubic-bezier(.175, .885, .32, 1) 100ms;
}

.e-play-icon::before {
    content: '\e798';
    font-size: 12px;
}

.e-bigger .e-play-icon::before {
    font-size: 14px;
}

.e-download-icon::before {
    content: '\e824';
}

#roundbtn .e-play-icon {
    margin-top: -2px;
}

.material #roundbtn .e-play-icon {
    margin-top: 0;
}

.check {
    display: -webkit-inline-box;
}

.margin {
    margin-left: 20px;
}
</style>

<style>
@import '../node_modules/@syncfusion/ej2-base/styles/material.css';
@import '../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css';
</style>

<script>
import Vue from 'vue';
import { ProgressButtonPlugin } from "@syncfusion/ej2-vue-splitbuttons";

Vue.use(ProgressButtonPlugin);

export default Vue.extend({
    data: function() {
        return {
            spinRight : { position: 'Right' },
            spinTop : { position: 'Top' },
            spinBottom : { position: 'Bottom' },
            spinCenter : { position: 'Center' },
            zoomOut : { effect: 'ZoomOut' },
            slideLeft : { effect: 'SlideLeft' },
            slideRight : { effect: 'SlideRight' },
            zoomIn : { effect: 'ZoomIn' }
        }
    },
    methods: {
        contractBegin: function() {
            this.$refs.contractBtn.ej2Instances.element.classList.add('e-round');
        },
        contractEnd: function() {
            this.$refs.contractBtn.ej2Instances.element.classList.remove('e-round');
        }
    }
});
</script>