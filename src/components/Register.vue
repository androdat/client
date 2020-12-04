<template>
  <div>
    <div
      style="display: none;"
      id="loader"
      class="loader_parent"
      v-bind:class="{ show: loader_show }"
    >
      <div class="loader"></div>
    </div>
    <div
      class="alert "
      v-bind:class="{ show: alert_show, red: !alert_color, green: alert_color }"
    >
      <div style="display:flex;">
        <p>{{ alert_msg }}</p>
        <p @click="(alert_show = !alert_show), refreshpage()" id="a">x</p>
      </div>
    </div>

    <div
      class="grid-container hide-for-mobile"
      v-bind:class="{ blur: loader_show }"
    >
      <div class="grid-item grid-item-1">
        <div class="footer">
          <h4>About NotchUp</h4>
          <div style="position:relative"></div>
          <div class="about-text">
            <p>
              NotchUp is an initiative by IIT-D IIM-A Alumni to inculcate
              critical new-age skills in children which will prepare them for a
              bright future. 65% of today's 5-year-old will in 15 years find
              themselves in jobs that don't exist today. More than 60 million of
              these new jobs will be in fields related to computer programming.
              NotchUp offers live interactive video classes from the comfort of
              your home which improve logical and problem solving skills by more
              than 75%.
            </p>
            <p>
              hello@notchup.co Registered Office - G-6, Namdhari Chambers, 9/54
              DB Gupta Road, Karol Bagh, Delhi 110005 © 2019 NotchUp Edu Private
              Ltd. All Rights Reserved
            </p>
            <h4 style="top:105%; left:0%">Follow Us!</h4>

            <div class="footer-container">
              <a href="https://www.facebook.com/Notchup.co/" target="_blank">
                <img src="../assets/facebook.png" alt class="footer-logo-img" />
              </a>

              <a href="https://twitter.com/notchupindia?" target="_blank">
                <img src="../assets/twitter.png" alt class="footer-logo-img" />
              </a>

              <a
                href="https://www.youtube.com/channel/UCd5-3Y7wqCCwITwQ7-2zB4g"
                target="_blank"
              >
                <img src="../assets/youtube.png" alt class="footer-logo-img" />
              </a>

              <a href="https://www.instagram.com/notchup.co/" target="_blank">
                <img
                  src="../assets/instagram.png"
                  alt
                  class="footer-logo-img"
                />
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="grid-item grid-item-2">
        <div class="logo">
          <img src="../assets/logo.png" alt />
        </div>

        <div class="nav">
          <p>About Us</p>
          <p>Online Coding</p>
          <p>Spoken English</p>
          <p>Group Classes</p>
          <p>Join Us</p>
          <p>Register</p>
        </div>
        <div class="heading">
          <p>Book Trial Class</p>
        </div>
      </div>
      <div class="grid-item grid-item-3">
        <div class="container">
          <div class="container-parent"></div>
          <div class="menu">
            <div class="ul-parent">
              <ul>
                <li>
                  <div
                    @click="menu(1)"
                    class="menu-item "
                    v-bind:class="{ menu_item_pressed: menu_item_one }"
                  >
                    <div class="number">
                      <div class="relative">
                        <p>1</p>
                      </div>
                    </div>
                    <div class="text">
                      <div class="relative">
                        <p>Profile</p>
                      </div>
                    </div>
                  </div>
                </li>

                <li>
                  <div
                    @click="menu(2)"
                    class="menu-item"
                    v-bind:class="{ menu_item_pressed: menu_item_two }"
                  >
                    <div class="number">
                      <div class="relative">
                        <p>2</p>
                      </div>
                    </div>
                    <div class="text">
                      <div class="relative">
                        <p>Course</p>
                      </div>
                    </div>
                  </div>
                </li>

                <li>
                  <div
                    @click="menu(3)"
                    class="menu-item"
                    v-bind:class="{ menu_item_pressed: menu_item_three }"
                  >
                    <div class="number">
                      <div class="relative">
                        <p>3</p>
                      </div>
                    </div>
                    <div class="text">
                      <div class="relative">
                        <p>TimeSlot</p>
                      </div>
                    </div>
                  </div>
                </li>

                <li>
                  <div
                    @click="menu(4)"
                    class="menu-item"
                    v-bind:class="{ menu_item_pressed: menu_item_four }"
                  >
                    <div class="number">
                      <div class="relative">
                        <p>4</p>
                      </div>
                    </div>
                    <div class="text">
                      <div class="relative">
                        <p>Review</p>
                      </div>
                    </div>
                  </div>
                </li>
              </ul>
            </div>
          </div>
          <!-- PROFILE -->
          <div  style="display:none" class="content" v-bind:class="{show: menu_item_one}">
            <div class="relative">
              <div class="header">
                <p>Fillout</p>
              </div>
              <form   @submit="fs" id="formsubmit" enctype=multipart/form-data>
           
              <div class="form-parent">
                    
                <ul>
                  <li>
                    <label for="fname" class="label">Parent's Name:</label>
                    <br />
                    <br />
                    <input
                      type="text"
                      
                      pattern="[a-zA-Z\s]+"
                      title="Eg:Ram Kumar"
                      required
                      v-model="pname"
                      
                      class="inputfield"
                    />
                    <br />
                    <br />
                  </li>
                  <li>
                    <label for="fname" class="label">Parent's Contact Number:</label>
                    <br />
                    <br />
                    <input
                      type="number"
                      
                      pattern="[0-9]{10}||[+][0-9]{12}||[0][0-9]{10}||[+][0-9]{12}||[0][0-9]{10}"
                      
                      title="Enter 10 digit number"
                      v-model="pphno"
                      class="inputfield"
                      required
                    />
                    <br />
                    <br />
                  </li>

                  <li>
                    <label for="fname" class="label">Parent's Email ID:</label>
                    <br />
                    <br />
                    <input
                      type="email"
                      v-model="pemail"
                      name="password"
                      class="inputfield"
                      required
                     
                    />
                    <br />
                    <br />
                  </li>
                </ul>

                <ul>
                  <li>
                    <label for="fname" class="label">Child's Name:</label>
                    <br />
                    <br />
                    <input
                      type="text"
                      v-model="cname"
                      name="text"
                      class="inputfield"
                      
                      pattern="[a-zA-Z\s]+"
                      title="Eg:Ram Kumar"
                      required
                    />
                    <br />
                    <br />
                  </li>
                  <li>
                    <label for="fname" class="label">Child's Age:</label>
                    <br />
                    <br />
                    <input
                      v-model="cage"
                      
                      class="inputfield"
                      
                      type="number"
                      pattern="[0-9]{2}"
                      title="Enter a number"
                      required
                    />
                    <br />
                    <br />
                  </li>
                </ul>
                 
              
              </div>
              <button  style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"> 
              <div   class="next" >
                
                       <div class="relative">
                  
                  <p>Next</p>
                </div>
                 
             
              </div>
               </button>
              </form>
            </div>
          </div>
          <!-- COURSE -->

          <div
            style="display:none"
            class="content"
            v-bind:class="{ show: menu_item_two }"
          >
            <div class="relative">
              <div class="header">
                <p>Select a course</p>
              </div>

              <div class="form-parent">
                <div class="ul-2">
                  <ul>
                    <li v-for="(course, index) in courses" :key="index">
                      <div
                        @click="selected(course.course_id)"
                        class="course-selection"
                        v-bind:ref="course.course_id"
                        v-bind:id="course.course_id"
                      >
                        <!--  v-bind:class="{course_selection_selected: course_selected}" -->
                        <p v-bind:ref="course.course_id">
                          {{ course.course_name }}
                        </p>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
              <button
                style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"
              >
                <div @click="menu(3)" class="next">
                  <div class="relative">
                    <p>Next</p>
                  </div>
                </div>
              </button>
            </div>
          </div>
          <!-- TIMESLOT -->
          <div
            style="display:none"
            class="content"
            v-bind:class="{ show: menu_item_three }"
          >
            <div class="relative">
              <div class="header">
                <p>Select a Time Slot</p>
              </div>

              <div class="form-parent">
                <div class="date-parent">
                  <div class="dates">
                    <ul>
                      <li v-for="(d, index) in final_timeslots" :key="index">
                        <div
                          @click="day_selected(index)"
                          class="date-val "
                          v-bind:class="{ timeslot_clicked: d.clicked }"
                        >
                          <div class="relative">
                            <p>{{ d.day }} {{ d.month }}</p>
                          </div>
                        </div>
                      </li>
                    </ul>
                  </div>
                </div>

                <div class="time-parent">
                  <div class="dates">
                    <ul>
                      <li v-for="(t, index) in final_time[0]" :key="index">
                        <div
                          @click="time_selected(index)"
                          v-bind:id="`controll${index}`"
                          class="time-val "
                        >
                          <div class="relative">
                            <p>{{ t }}</p>
                          </div>
                        </div>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
              <button
                style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"
              >
                <div @click="menu(4)" class="next">
                  <div class="relative">
                    <p>Next</p>
                  </div>
                </div>
              </button>
            </div>
          </div>

          <!-- REVIEW -->
          <div
            style="display:none"
            class="content"
            v-bind:class="{ show: menu_item_four }"
          >
            <div class="relative">
              <div class="header">
                <p>Confirm Details</p>
              </div>

              <div class="form-parent">
                <table>
                  <tr>
                    <th>Parent's Name</th>
                    <td>{{ this.pname }}</td>
                  </tr>
                  <tr>
                    <th>Parent's Contact Number</th>
                    <td>{{ this.pphno }}</td>
                  </tr>
                  <tr>
                    <th>Parent's Email ID</th>
                    <td>{{ this.pemail }}</td>
                  </tr>
                  <tr>
                    <th>Child's Name</th>
                    <td>{{ this.cname }}</td>
                  </tr>
                  <tr>
                    <th>Child's Age</th>
                    <td>{{ this.cage }}</td>
                  </tr>
                  <tr>
                    <th>Course</th>
                    <td>{{ this.selected_course }}</td>
                  </tr>
                  <tr>
                    <th>Time Slot</th>
                    <td>
                      {{ get_Date(this.selected_timeslot).day }}
                      {{ get_Date(this.selected_timeslot).month }}
                      {{ get_Date(this.selected_timeslot).time }}
                    </td>
                  </tr>
                </table>
              </div>
              <button
                style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"
              >
                <div @click="post" class="next">
                  <div class="relative">
                    <p>Submit</p>
                  </div>
                </div>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="grid-container-mobile hide-for-dekstop">
      <div class="grid-item grid-item-1-mobile">
        <div class="logo">
          <img class="img-resize" src="../assets/logo.png" alt />
        </div>
        <div class="hb">
          <a id="btnhb" href="#" class="hamburger hide-for-dekstop">
            <span></span>
            <span></span>
            <span></span>
          </a>
        </div>
      </div>

      <div class="grid-item grid-item-2-mobile">
        <div
          @click="menu(1)"
          class="menu-item "
          v-bind:class="{ menu_item_pressed: true }"
        >
          <div class="number">
            <div class="relative">
              <p>{{ header_count }}</p>
            </div>
          </div>
          <div class="text">
            <div class="relative">
              <p>{{ header_text }}</p>
            </div>
          </div>
        </div>

        <!-- PROFILE -->
        <div  style="display:none" class="content" v-bind:class="{show: menu_item_one}">
            <div class="relative">
              <div class="header">
                <p>Fillout</p>
              </div>
              <form   @submit="fs" id="formsubmit" enctype=multipart/form-data>
           
              <div class="form-parent">
                    
                <ul>
                  <li>
                    <label for="fname" class="label">Parent's Name:</label>
                    <br />
                    <br />
                    <input
                      type="text"
                      
                      pattern="[a-zA-Z\s]+"
                      title="Eg:Ram Kumar"
                      required
                      v-model="pname"
                      
                      class="inputfield"
                    />
                    <br />
                    <br />
                  </li>
                  <li>
                    <label for="fname" class="label">Parent's Contact Number:</label>
                    <br />
                    <br />
                    <input
                      type="tel"
                      
                      pattern="[0-9]{10}||[+][0-9]{12}||[0][0-9]{10}||[+][0-9]{12}||[0][0-9]{10}"
                      
                      title="Enter 10 digit number"
                      v-model="pphno"
                      class="inputfield"
                      required
                    />
                    <br />
                    <br />
                  </li>

                  <li>
                    <label for="fname" class="label">Parent's Email ID:</label>
                    <br />
                    <br />
                    <input
                      type="email"
                      v-model="pemail"
                      name="password"
                      class="inputfield"
                      required
                     
                    />
                    <br />
                    <br />
                  </li>
                </ul>

                <ul>
                  <li>
                    <label for="fname" class="label">Child's Name:</label>
                    <br />
                    <br />
                    <input
                      type="text"
                      v-model="cname"
                      name="text"
                      class="inputfield"
                      
                      pattern="[a-zA-Z\s]+"
                      title="Eg:Ram Kumar"
                      required
                    />
                    <br />
                    <br />
                  </li>
                  <li>
                    <label for="fname" class="label">Child's Age:</label>
                    <br />
                    <br />
                    <input
                      v-model="cage"
                      
                      class="inputfield"
                      
                      type="number"
                      pattern="[0-9]{2}"
                      title="Enter a number"
                      required
                    />
                    <br />
                    <br />
                  </li>
                </ul>
                 
              
              </div>
              <button  style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"> 
              <div   class="next" >
                
                       <div class="relative">
                  
                  <p>Next</p>
                </div>
                 
             
              </div>
               </button>
              </form>
            </div>
          </div> 

        <!-- COURSE -->

        <div
          style="display:none"
          class="content"
          v-bind:class="{ show: menu_item_two }"
        >
          <div class="relative">
            <div class="header">
              <p>Select a course</p>
            </div>

            <div class="form-parent">
              <div class="ul-2">
                <ul>
                  <li v-for="(course, index) in courses" :key="index">
                    <div
                      @click="selected(course.course_id)"
                      class="course-selection"
                      v-bind:ref="course.course_id"
                      v-bind:id="course.course_id"
                    >
                      <!--  v-bind:class="{course_selection_selected: course_selected}" -->
                      <p v-bind:ref="course.course_id">
                        {{ course.course_name }}
                      </p>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
            <button
              style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"
            >
              <div @click="menu(3)" class="next">
                <div class="relative">
                  <p>Next</p>
                </div>
              </div>
            </button>
          </div>
        </div>

        <!-- TIMESLOT -->
        <div
          style="display:none"
          class="content"
          v-bind:class="{ show: menu_item_three }"
        >
          <div class="relative">
            <div class="header">
              <p>Select a Tome Slot</p>
            </div>

            <div class="form-parent">
              <div class="date-parent">
                <div class="dates">
                  <ul>
                    <li v-for="(d, index) in final_timeslots" :key="index">
                      <div
                        @click="day_selected(index)"
                        class="date-val "
                        v-bind:class="{ timeslot_clicked: d.clicked }"
                      >
                        <div class="relative">
                          <p>{{ d.day }} {{ d.month }}</p>
                        </div>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>

              <div class="time-parent">
                <div class="dates">
                  <ul>
                    <li v-for="(t, index) in final_time[0]" :key="index">
                      <div
                        @click="time_selected(index)"
                        v-bind:id="`controll${index}`"
                        class="time-val "
                      >
                        <div class="relative">
                          <p>{{ t }}</p>
                        </div>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
            <button
              style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"
            >
              <div @click="menu(4)" class="next">
                <div class="relative">
                  <p>Next</p>
                </div>
              </div>
            </button>
          </div>
        </div>

        <!-- REVIEW -->
        <div
          style="display:none"
          class="content"
          v-bind:class="{ show: menu_item_four }"
        >
          <div class="relative">
            <div class="header">
              <p>Confirm Details</p>
            </div>

            <div class="form-parent">
              <table>
                <tr>
                  <th>Parent's Name</th>
                </tr>
                <tr>
                  <td>{{ this.pname }}</td>
                </tr>
                <tr>
                  <th>Parent's Contact Number</th>
                </tr>
                <tr>
                  <td>{{ this.pphno }}</td>
                </tr>

                <tr>
                  <th>Parent's Email ID</th>
                </tr>
                <tr>
                  <td>{{ this.pemail }}</td>
                </tr>

                <tr>
                  <th>Child's Name</th>
                </tr>
                <tr>
                  <td>{{ this.cname }}</td>
                </tr>

                <tr>
                  <th>Child's Age</th>
                </tr>
                <tr>
                  <td>{{ this.cage }}</td>
                </tr>

                <tr>
                  <th>Course</th>
                </tr>
                <tr>
                  <td>{{ this.selected_course }}</td>
                </tr>

                <tr>
                  <th>Time Slot</th>
                </tr>
                <tr>
                  <td>
                    {{ get_Date(this.selected_timeslot).day }}
                    {{ get_Date(this.selected_timeslot).month }}
                    {{ get_Date(this.selected_timeslot).time }}
                  </td>
                </tr>
              </table>
            </div>
            <button
              style="background: none; color: inherit; border: none; padding: 0; font: inherit; cursor: pointer; outline: inherit;"
            >
              <div @click="post" class="next">
                <div class="relative">
                  <p>Submit</p>
                </div>
              </div>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "Register",

  async mounted() {
    //  document.body.style.zoom = "80%";
    let res = await axios.get(
      "https://script.google.com/macros/s/AKfycbzJ8Nn2ytbGO8QOkGU1kfU9q50RjDHje4Ysphyesyh-osS76wep/exec"
    );
    // console.log(res.data)
    this.data = res.data;
    for (var i = 0; i < res.data.length; i++) {
      let val = {
        course_id: res.data[i].course_id,
        course_name: res.data[i].course_name
      };
      this.courses.push(val);
    }
  },

  data() {
    return {
      data: [],
      timeslots: [],
      courses: [],
      final_timeslots: [],
      final_time: [],
      pname: "",
      pphno: null,
      pemail: "",
      cname: "",
      cage: null,
      selected_course_id: null,
      selected_course: "",
      selected_timeslot: null,
      menu_item_one: true,
      menu_item_two: false,
      menu_item_three: false,
      menu_item_four: false,
      course_selected: false,
      form_filled: false,
      header_count: 1,
      header_text: "Profile",
      alert_msg: "",
      alert_show: false,
      alert_color: null,
      loader_show: false,
      reset: false
    };
  },

  methods: {
    clear_inline() {
      this.$refs[1][0].style.color = "#1e63bd";
      this.$refs[1][0].style.fontWeight = "normal";
      this.$refs[1][1].style.backgroundColor = "white";

      this.$refs[2][0].style.color = "#1e63bd";
      this.$refs[2][0].style.fontWeight = "normal";
      this.$refs[2][1].style.backgroundColor = "white";

      this.$refs[3][0].style.color = "#1e63bd";
      this.$refs[3][0].style.fontWeight = "normal";
      this.$refs[3][1].style.backgroundColor = "white";

      this.$refs[4][0].style.color = "#1e63bd";
      this.$refs[4][0].style.fontWeight = "normal";
      this.$refs[4][1].style.backgroundColor = "white";

      this.$refs[5][0].style.color = "#1e63bd";
      this.$refs[5][0].style.fontWeight = "normal";
      this.$refs[5][1].style.backgroundColor = "white";
    },
    selected(c_id) {
      //CSS
      this.clear_inline();
      this.$refs[c_id][0].style.color = "white";
      this.$refs[c_id][0].style.fontWeight = "bold";
      this.$refs[c_id][1].style.backgroundColor = "#1e63bd";
      this.timeslots = [];
      this.course_selected = true;
      // Filling timeslots according to course selection
      for (var i = 0; i < this.data.length; i++) {
        if (this.data[i].course_id == c_id) {
          for (var k = 0; k < this.data[i].slots.length; k++) {
            this.timeslots.push(this.data[i].slots[k].slot);
          }
        }
      }
      // Setting coursename variable
      for (var j = 0; j < this.courses.length; j++) {
        if (c_id == this.courses[j].course_id) {
          this.selected_course = this.courses[j].course_name;
          this.selected_course_id = c_id;
        }
      }

      this.filter();
    },

    filter() {
      //Filtering Time by constraints
      this.final_timeslots = [];

      let current_time = Date.now();

      let ll = current_time + 14400 * 1000;
      let ul = current_time + 604800 * 1000;

      let copy_timeslots = this.timeslots;

      this.timeslots = filterByLimits(this.timeslots, ul, ll);

      if (this.timeslots.length == 0) {
        this.timeslots = copy_timeslots;
      }
      //Creating Object
      let temp_array = [];
      for (var i = 0; i < this.timeslots.length; i++) {
        this.get_Date(this.timeslots[i]);
        temp_array.push(this.get_Date(this.timeslots[i]));
      }

      let date = [];
      for (var x = 0; x < temp_array.length; x++) {
        date.push(temp_array[x].day.toString() + " " + temp_array[x].month);
      }

      var unique = date.filter(onlyUnique);

      for (var y = 0; y < unique.length; y++) {
        let res = unique[y].split(" ");
        let da = res[0];
        let mo = res[1];

        let obj = {
          day: da,
          month: mo,
          clicked: false,
          time: [],
          timestamp: []
        };

        for (var z = 0; z < temp_array.length; z++) {
          if (temp_array[z].day == da && temp_array[z].month == mo) {
            obj.time.push(temp_array[z].time);
            obj.timestamp.push(temp_array[z].timestamp);
          }
        }

        this.final_timeslots.push(obj);
      }
    },

    day_selected(i) {
      //CSS
      for (let i = 0; i < this.final_timeslots.length; i++) {
        this.final_timeslots[i].clicked = false;
      }
      this.final_timeslots[i].clicked = true;
      //Show time slot of date selected
      this.final_time = [];

      this.final_time.push(this.final_timeslots[i].time);
      this.final_time.push(this.final_timeslots[i].timestamp);
    },

    time_selected(i) {
      //CSS
      for (let i = 0; i < this.final_time[0].length; i++) {
        if (window[`controll${i}`][0].classList.contains("timeslot_clicked")) {
          window[`controll${i}`][0].classList.remove("timeslot_clicked");
        }

        if (window[`controll${i}`][1].classList.contains("timeslot_clicked")) {
          window[`controll${i}`][1].classList.remove("timeslot_clicked");
        }
      }
      window[`controll${i}`][0].classList.add("timeslot_clicked");
      window[`controll${i}`][1].classList.add("timeslot_clicked");
      //Set time selected

      this.selected_timeslot = this.final_time[1][i];
    },

    getIst(UNIX_timestamp) {
      const dateObject = new Date(UNIX_timestamp * 1);
      const humanDateFormat = dateObject.toLocaleString(undefined, {
        timeZone: "Asia/Kolkata"
      });

      return humanDateFormat;
    },
    get_Date(UNIX_timestamp) {
      // To convert unix time stamp to readable format
      const dateObject = new Date(UNIX_timestamp * 1);
      const humanDateFormat = dateObject.toLocaleString(undefined, {
        timeZone: "Asia/Kolkata"
      });
      var months_arr = [
        "Jan",
        "Feb",
        "Mar",
        "Apr",
        "May",
        "Jun",
        "Jul",
        "Aug",
        "Sep",
        "Oct",
        "Nov",
        "Dec"
      ];
      var my_date = new Date(humanDateFormat);
      var month = months_arr[my_date.getMonth()];
      var day = my_date.getDate();

      var hours = my_date.getHours();
      var minutes = "0" + my_date.getMinutes();

      var convdataTime = hours + ":" + minutes.substr(-2);

      let val = {
        day: day,
        month: month,
        time: tConvert(convdataTime),
        timestamp: UNIX_timestamp
      };

      return val;
    },

    fs(e) {
      //Handling form submit
      e.preventDefault();
      // let params = {
      //   pname: this.pname,
      //   pphno: this.pphno,
      //   pemail: this.pemail,
      //   cname: this.cname,
      //   cage: this.cage,
      //   selected_course_id: this.selected_course_id,
      //   selected_course: this.selected_course,
      //   selected_timeslot:this.selected_timeslot

      // };
      this.form_filled = true;
      this.menu(2);
    },
    menu(x) {
      if (x == 1) {
        this.menu_item_one = true;
        this.menu_item_two = false;
        this.menu_item_three = false;
        this.menu_item_four = false;
      }

      if (x == 2) {
        if (this.form_filled == true) {
          this.header_count = 2;
          this.header_text = "Course";

          this.menu_item_one = false;
          this.menu_item_two = true;
          this.menu_item_three = false;
          this.menu_item_four = false;
        }
      }
      if (x == 3) {
        if (this.selected_course_id != null) {
          this.header_count = 3;
          this.header_text = "TimeSlot";

          this.menu_item_one = false;
          this.menu_item_two = false;
          this.menu_item_three = true;
          this.menu_item_four = false;
        } else {
          this.alert_msg = "Select a Course to Continue";
          this.alert_show = !this.alert_show;
          this.alert_color = false;
        }
      }
      if (x == 4) {
        if (this.selected_timeslot != null) {
          this.header_count = 4;
          this.header_text = "Review";

          this.menu_item_one = false;
          this.menu_item_two = false;
          this.menu_item_three = false;
          this.menu_item_four = true;
        } else {
          this.alert_msg = "Select a TimeSlot to Continue";
          this.alert_show = !this.alert_show;
          this.alert_color = false;
        }
      }
    },
    async post() {
      this.loader_show = true;

      let params = {
        parentName: this.pname,
        contactNo: this.pphno,
        emailId: this.pemail,
        childName: this.cname,
        childAge: this.cage,
        courseId: this.selected_course_id,
        courseName: this.selected_course,
        timestamp: this.selected_timeslot
      };
      // https://notch-backend.herokuapp.com/getAllData

      let res = await axios.post(
        "https://notch-backend.herokuapp.com/registerStudent",
        params
      );
      this.loader_show = false;

      if (res.data == "Successfully Posted") {
        this.alert_msg = "Registration Successfull";
        this.alert_show = !this.alert_show;
        this.alert_color = true;
        this.reset = true;
      }
      if (res.data == "error") {
        this.alert_msg = "Registration Failed ";
        this.alert_show = !this.alert_show;
        this.alert_color = false;
        this.reset = true;
      }
    },
    refreshpage() {
      if (this.reset == true) {
        this.$router.go();
      }
    }
  }
};
// vanilla js functions
const filterByLimits = (arr = [], upper, lower) => {
  let res = [];
  res = arr.filter(el => {
    return el >= lower && el <= upper;
  });
  return res;
};

function tConvert(time) {
  // Check correct time format and split into components
  time = time.toString().match(/^([01]\d|2[0-3])(:)([0-5]\d)(:[0-5]\d)?$/) || [
    time
  ];

  if (time.length > 1) {
    // If time format correct
    time = time.slice(1); // Remove full string match value
    time[5] = +time[0] < 12 ? "AM" : "PM"; // Set AM/PM
    time[0] = +time[0] % 12 || 12; // Adjust hours
  }
  return time.join(""); // return adjusted time or original string
}

function onlyUnique(value, index, self) {
  return self.indexOf(value) === index;
}
</script>

<style lang="scss" scoped>
/* PAGE LOAD ANIMATION */
@-webkit-keyframes spin {
  0% {
    -webkit-transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
  }
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

.loader {
  border: 8px solid #f3f3f3;
  border-radius: 50%;
  border-top: 8px solid #195ed8;
  width: 60px;
  height: 60px;
  -webkit-animation: spin 2s linear infinite; /* Safari */
  animation: spin 2s linear infinite;

  z-index: 4;
}

.loader_parent {
  z-index: 4;
  width: fit-content;
  height: fit-content;
  position: absolute;

  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) !important;
}
.blur {
  filter: blur(3px);
}
.green {
  border: solid 2px #32b32e !important;
}
.red {
  border: solid 2px #eb1818 !important;
}
#a {
  margin-left: 20px;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
  font-size: 22px;
}
#a:hover {
  // color: #2b2c2e;
  transform: scale(1.2);
}
.alert {
  display: none !important;
  padding: 20px;
  z-index: 1;
  width: auto;
  height: auto;
  border: solid 2px #1e63bd;
  background-color: white;
  position: absolute;
  top: 23%;
  left: 42%;
  transform: translate(-50%, -50%);
  // display: flex;
  // justify-content: space-around;

  p {
    margin: 0;
    font-family: "Montserrat", sans-serif;
    font-weight: bold;
    font-size: 20px;
    line-height: 24px;
    color: black;
    text-align: center;
  }
}
.relative {
  position: relative;
  width: 100%;
  height: 100%;
}
h1 {
  color: green;
  margin: 0;
  padding: 0;
}

.grid-container {
  display: grid;
  grid-template-columns: 80% 20%;
  grid-template-rows: 25vh 75vh;
}

.grid-item-1 {
  grid-column-start: 2;
  grid-column-end: 3;
  grid-row-start: 1;
  grid-row-end: 3;
  //  border: solid red;
  height: auto;
  overflow: auto;

  position: relative;
  background-color: #1e63bd;
}

.grid-item-2 {
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 1;
  grid-row-end: 2;
  // border: solid red;

  position: relative;
}

.grid-item-3 {
  grid-column-start: 1;
  grid-column-end: 2;
  grid-row-start: 2;
  grid-row-end: 3;
  // border: solid red;

  position: relative;
}

.footer {
  width: 100%;
  height: 100%;
  // height: fit-content;
  background-color: #1e63bd;
}

h4 {
  width: fit-content;
  position: absolute;
  left: 10%;
  top: 6%;
  // transform: translate(-50%, -50%);
  margin: 0;
  padding: 0;
  font-family: "Montserrat", sans-serif;
  font-weight: bold;
  font-size: 26px;
  color: white;
}

@media screen and (max-width: 1200px) {
  h4 {
    width: fit-content;
    position: absolute;
    left: 10%;
    top: 6%;
    // transform: translate(-50%, -50%);
    margin: 0;
    padding: 0;
    font-family: "Montserrat", sans-serif;
    font-weight: bold;
    font-size: 20px;
    color: white;
  }

  .footer-container {
    width: 320px;
    width: 100%;
    height: 49px;
    background-color: white;
    -webkit-box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    border-radius: 7px;
    position: absolute;
    left: 50%;
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
    top: 113% !important;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -ms-flex-pack: distribute;
    justify-content: space-around;
  }

  .logo {
    width: 83px !important;
    height: 83px !important;
  }
}

.about-text {
  width: 80%;
  height: fit-content;
  // border: dotted red;
  position: absolute;
  left: 10%;
  top: 10%;
  // transform: translate(-50%, -50%);
  p {
    font-family: "Montserrat", sans-serif;
    font-weight: 500;
    font-size: 13px;
    line-height: 24px;
    color: white;
    text-align: left;
  }
}

.footer-container {
  width: 320px;
  width: 100%;
  height: 49px;
  background-color: white;
  -webkit-box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 7px;
  position: absolute;
  left: 50%;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
  top: 120%;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -ms-flex-pack: distribute;
  justify-content: space-around;
}

.footer-logo-img {
  width: 33px;
  height: 33px;
  margin-top: 8px;
  -webkit-filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
}

.logo {
  width: 99px;
  height: 104px;
  // border: solid green;
  position: absolute;
  left: 5%;
  top: 30%;
  transform: translate(-50%, -50%);
  //  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
}

.nav {
  width: 85%;
  height: 104px;
  //  border: solid green;
  position: absolute;
  left: 54%;
  top: 30%;
  transform: translate(-50%, -50%);

  display: flex;
  justify-content: space-evenly;

  p {
    font-family: "Montserrat", sans-serif;
    font-weight: bold;
    font-size: 23px;

    color: #1e63bd;
  }
}

.heading {
  width: fit-content;
  height: fit-content;
  position: absolute;
  left: 2%;
  top: 83%;

  // border: solid green;

  p {
    margin: 0;
    padding: 0;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 55px;

    color: #1e63bd;
  }
}

.container {
  width: 92%;
  height: 75%;
  // border: solid purple;

  position: absolute;
  left: 48.5%;
  top: 52%;
  transform: translate(-50%, -50%);
}
.container-parent {
  width: 100%;
  height: 100%;
  // border: dotted red;
  position: relative;
}

.menu {
  width: 30%;
  height: 100%;
  // border: dotted red;

  position: absolute;
  left: 15%;
  top: 50%;
  transform: translate(-50%, -50%);
}

.ul-parent {
  // margin: 4% auto;
  // border: solid yellow;
  width: 100%;
  height: 100%;
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }

  li:not(:last-child) {
    padding-bottom: 48px;
  }
}

.menu-item {
  width: 92%;

  height: 63px;
  min-width: 228.5px;
  width: auto;
  max-width: 88%;
  border: solid 2px #1e63bd;
  background: white;
  position: relative;
}
.menu-item:hover {
  cursor: pointer;
  .text {
    background: #1e63bd;
    .relative {
      p {
        color: white;
        font-weight: 500;
      }
    }
  }
}

.menu_item_pressed {
  cursor: pointer;
  .text {
    background: #1e63bd;
    .relative {
      p {
        color: white;
        font-weight: 500;
      }
    }
  }
}

.number {
  width: 20%;
  height: 100%;
  background: #cde1fa;
  border-right: solid 2px #1e63bd;
  p {
    margin: 0;
    padding: 0;

    font-family: "Montserrat", sans-serif;
    font-weight: 500;
    font-size: 55px;

    color: #1e63bd;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
}

.text {
  width: 80%;
  height: 100%;
  background: none;
  position: absolute;
  left: 60%;
  top: 50%;
  transform: translate(-50%, -50%);

  p {
    margin: 0;
    padding: 0;

    font-family: "Montserrat", sans-serif;
    font-weight: 500;
    font-size: 33px;

    color: #1e63bd;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
}

.content {
  width: 67%;
  height: 100%;
  border: solid 2px #1e63bd;

  position: absolute;
  left: 66%;
  top: 50%;
  transform: translate(-50%, -50%);
}

.next {
  cursor: pointer;
  position: absolute;
  left: 50%;
  top: 100%;
  transform: translate(-50%, -50%);
  background: #1e63bd;
  width: 15%;
  height: 11%;

  p {
    margin: 0;
    padding: 0;
    font-family: "Montserrat", sans-serif;
    font-weight: bold;
    font-size: 21px;

    color: white;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
}

.next:hover {
  p {
    font-size: 24px;
  }
}

.header {
  height: fit-content;
  width: fit-content;
  position: absolute;
  left: 4%;
  top: 2%;

  p {
    margin: 0;
    padding: 0;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 30px;

    color: black;

    // position: absolute;
    // left: 50%;
    // top: 50%;
    // transform: translate(-50%, -50%);
  }
}

.form-parent {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  width: 90%;
  height: 70%;
  // border: dotted red;

  position: absolute;
  left: 4%;
  top: 14%;
  // transform: translate(-50%, -50%);

  ul {
    list-style: none;

    margin: 0;
    padding: 0;
  }

  li {
    // padding:2rem;
    // margin: 1rem;
    // padding-right: 10px;
    // padding-bottom: 10px;
    // padding: 3px;
  }
}

.label {
  font-family: "Montserrat", sans-serif;
  font-weight: normal;
  font-size: 20px;
  color: #1e63bd;
  margin-bottom: 4px;
}

.inputfield {
  border: solid 1px #1e63bd;
  width: 250px;
  height: 35px;
  font-size: 16px;
  font-family: "Montserrat", sans-serif;
}
@media screen and (max-width: 1200px) {
  .inputfield {
    border: solid 1px #1e63bd;
    width: auto;
    height: 35px;
    font-size: 16px;
    font-family: "Montserrat", sans-serif;
  }
}

.ul-2 {
  ul {
    margin: 0;
    padding: 0;
    margin-top: 6%;
    list-style: none;
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
  }
  li {
    padding: 0;
    padding-right: 4%;
    padding-bottom: 4%;
  }
}

.course-selection {
  width: 195px;
  height: 72px;
  border: solid 2px #1e63bd;
  position: relative;
  p {
    margin: 0;
    padding: 0;
    width: fit-content;
    height: fit-content;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 18px;

    color: #1e63bd;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
}

.course-selection:hover {
  cursor: pointer;
  width: 195px;
  height: 72px;
  border: solid 2px #1e63bd;
  background-color: #1e63bd;
  position: relative;
  p {
    margin: 0;
    padding: 0;
    width: fit-content;
    height: fit-content;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 18px;

    color: white;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    font-weight: bold;
  }
}
.course_selection_selected {
  cursor: pointer;
  width: 223px;
  height: 82px;
  border: solid 2px #1e63bd;
  background-color: #1e63bd;
  position: relative;
  p {
    margin: 0;
    padding: 0;
    width: fit-content;
    height: fit-content;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 21px;

    color: white;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    font-weight: bold;
  }
}

.date-parent {
  overflow: auto;
  width: 100%;

  max-height: 147.391px;
  // border: dotted red;

  position: absolute;
  left: 50%;
  top: 25%;
  transform: translate(-50%, -50%);

  ul {
    margin: 0;
    padding: 0;

    list-style: none;
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
  }
  li {
    padding: 0;
  }
  li:not(:last-child) {
    padding-right: 3%;
    padding-bottom: 3%;
  }
}

.date-val {
  height: 80px;
  width: 76px;
  border: solid 2px #1e63bd;
  p {
    text-align: center;
    margin: 0;
    padding: 0;
    // width: fit-content;
    height: fit-content;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 18px;

    color: #1e63bd;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    font-weight: bold;
  }
}

.date-val:hover {
  cursor: pointer;

  background-color: #1e63bd;

  p {
    color: white;
  }
}

.time-parent {
  overflow: auto;
  width: 90%;

  max-height: 175px;
  // border: dotted red;

  position: absolute;
  left: 50%;
  top: 77%;
  transform: translate(-50%, -50%);

  ul {
    margin: 0;
    padding: 0;

    list-style: none;
    display: flex;
    justify-content: flex-start;
    flex-wrap: wrap;
  }
  li {
    padding: 0;
    padding-bottom: 2%;
    padding-right: 2%;
  }
  li:not(:last-child) {
    // padding-right: 4%;
    // padding-bottom: 4%;
  }
}

.time-val {
  height: 45px;
  width: 130px;
  border: solid 2px #1e63bd;
  p {
    text-align: center;
    margin: 0;
    padding: 0;
    width: fit-content;
    height: fit-content;
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 18px;

    color: #1e63bd;

    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    font-weight: bold;
  }
}

.time-val:hover {
  cursor: pointer;

  background-color: #1e63bd;

  p {
    color: white;
  }
}

table {
  width: 100%;
}
th {
  font-family: "Montserrat", sans-serif;
  font-weight: bold;
  font-size: 18px;

  color: #1e63bd;
}
td {
  font-family: "Montserrat", sans-serif;
  font-weight: normal;
  font-size: 18px;

  color: black;
}

th,
td {
  // border: solid 2px black;
  width: 50%;
  text-align: left;
  padding: 1%;
}

.show {
  display: block !important;
}

.timeslot_clicked {
  background-color: #1e63bd;

  p {
    color: white;
  }
}

// MEDIA QUERIES

@media screen and (max-width: 1000px) {
  .hide-for-mobile {
    display: none !important;
  }

  .grid-container-mobile {
    display: grid;
    grid-template-columns: 100%;
    grid-template-rows: 10vh 90vh 1vh;
  }

  .grid-item-1-mobile {
    //border: solid red;
    position: relative;
  }

  .grid-item-2-mobile {
    // border: solid red;
    position: relative;
    overflow: scroll;
  }
  .img-resize {
    width: 65px;
    height: 68px;
  }

  .logo[data-v-7bf3755a] {
    width: 99px !important;
    height: 104px !important;
    position: absolute !important;
    left: 12% !important;
    top: 60% !important;
    transform: translate(-50%, -50%) !important;
  }

  .hamburger span {
    display: block;
    width: 50px;
    height: 7px;
    background-color: #195ed8;
    -webkit-transition: all 300ms ease-in-out;
    transition: all 300ms ease-in-out;
    -webkit-transform-origin: 4px 1px;
    transform-origin: 4px 1px;
  }

  .hamburger span:not(:last-child) {
    margin-bottom: 5px;
  }

  .hb {
    position: absolute;
    top: 23%;
    right: 5%;
  }
  .menu-item[data-v-7bf3755a] {
    width: 92%;
    height: 63px;
    min-width: 228.5px;
    width: auto;
    max-width: 88%;
    border: solid 2px #1e63bd;
    background: white;
    position: relative;
    margin: 16px auto;
  }

  .content[data-v-7bf3755a] {
    width: 90%;
    height: 80%;
    border: solid 2px #1e63bd;
    position: absolute;
    left: 50%;
    top: 61%;
    transform: translate(-50%, -50%);
    // overflow: auto;
  }

  .form-parent[data-v-7bf3755a] {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    width: 90%;
    height: 85%;
    // border: dotted red;
    position: absolute;
    left: 4%;
    top: 8%;
    overflow: auto;
  }
  .next[data-v-7bf3755a] {
    cursor: pointer;
    position: absolute;
    left: 50%;
    top: 100%;
    transform: translate(-50%, -50%);
    background: #1e63bd;
    width: 29%;
    height: 9%;
  }

  .ul-2 ul[data-v-7bf3755a] {
    margin: 0;
    padding: 0;
    margin-top: 6%;
    list-style: none;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }

  .time-parent[data-v-7bf3755a] {
    overflow: auto;
    width: 90%;
    max-height: 175px;
    // border: dotted red;
    position: absolute;
    left: 50%;
    top: 68%;
    transform: translate(-50%, -50%);
  }

  .time-val[data-v-7bf3755a] {
    height: 45px;
    width: 125px;
    border: solid 2px #1e63bd;
  }

  .time-parent ul[data-v-7bf3755a] {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
  }
  .alert {
    left: 50% !important;
  }
  .next:hover {
    p {
      font-size: 21px;
    }
  }
}

@media (min-width: 64em) {
  .hide-for-dekstop {
    display: none;
  }
}

@media (width: 415px) {
  .label[data-v-7bf3755a] {
    font-family: "Montserrat", sans-serif;
    font-weight: normal;
    font-size: 18px;
    color: #1e63bd;
    margin-bottom: 4px;
  }

  .inputfield[data-v-7bf3755a] {
    border: solid 1px #1e63bd;
    width: auto;
    height: 27px;
    font-size: 16px;
    font-family: "Montserrat", sans-serif;
  }
}
</style>
