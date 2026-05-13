import { useState, useEffect, useCallback } from "react";
 
/* ─── PALETTE ──────────────────────────────────────────────────── */
const S={headerBg:"#4a7db5",rowOdd:"#f5f8fc",rowEven:"#ffffff",border:"#d0d8e4",borderDark:"#b0bac8",gradeGreen:"#2a7a2a",navBg:"#3d6fa8",navActive:"#2a5490",link:"#2255aa",missing:"#cc0000",grayLabel:"#555e6b",sectionHdr:"#dce6f0",sectionBdr:"#a8bedc",white:"#ffffff",body:"#f0f4f8",text:"#1a2333",muted:"#667788",orange:"#e07800"};
const CAT_COLORS={Test:"#d32f2f",Quiz:"#1565c0",Homework:"#2e7d32",Project:"#6a1b9a",Participation:"#00838f",Lab:"#e65100"};
 
/* ─── INITIAL DB (in-memory, persists during session) ────────────*/
const initDB = () => ({
  users: [
    {id:"u0",email:"history@realworld.biz",pass:"duty6556",role:"admin",name:"Super Admin"},
    {id:"u1",email:"lpuffer@school.edu",pass:"math1234",role:"teacher",name:"Lindsay Puffer",teacherId:"t1"},
    {id:"u2",email:"cday@school.edu",pass:"english99",role:"teacher",name:"Courtney Day",teacherId:"t2"},
    {id:"u3",email:"jwieland@school.edu",pass:"science7",role:"teacher",name:"Joseph Wieland",teacherId:"t3"},
    {id:"u4",email:"jordan.m@student.fcps.edu",pass:"student123",role:"student",name:"Jordan Mitchell",studentId:"s1"},
    {id:"u5",email:"noah.a@student.fcps.edu",pass:"student123",role:"student",name:"Noah Anderson",studentId:"s2"},
    {id:"u6",email:"emma.b@student.fcps.edu",pass:"student123",role:"student",name:"Emma Brown",studentId:"s3"},
  ],
  teachers: [
    {id:"t1",name:"Lindsay Puffer",email:"lpuffer@school.edu",room:"M012",subject:"Mathematics"},
    {id:"t2",name:"Courtney Day",email:"cday@school.edu",room:"M302",subject:"English"},
    {id:"t3",name:"Joseph Wieland",email:"jwieland@school.edu",room:"L149",subject:"Life Science"},
  ],
  students: [
    {id:"s1",last:"Mitchell",first:"Jordan",grade:"7",dob:"03/14/2012",locker:"B-227",bus:"Route 42",counselor:"Mrs. Harper",phone:"(703)555-0182",email:"jordan.m@student.fcps.edu"},
    {id:"s2",last:"Anderson",first:"Noah",grade:"7",dob:"01/22/2012",locker:"B-228",bus:"Route 12",counselor:"Mrs. Harper",phone:"(703)555-0183",email:"noah.a@student.fcps.edu"},
    {id:"s3",last:"Brown",first:"Emma",grade:"7",dob:"05/05/2012",locker:"B-229",bus:"Route 7",counselor:"Mr. Davis",phone:"(703)555-0184",email:"emma.b@student.fcps.edu"},
  ],
  courses: [
    {id:"c1",name:"Mathematics 7",period:"5",room:"M012",teacherId:"t1",studentIds:["s1","s2","s3"],
      weights:{Test:40,Quiz:25,Homework:20,Project:10,Participation:5},
      categories:["Test","Quiz","Homework","Project","Participation"]},
    {id:"c2",name:"English 7 HN",period:"2",room:"M302",teacherId:"t2",studentIds:["s1","s3"],
      weights:{Test:50,Quiz:20,Homework:20,Project:10},
      categories:["Test","Quiz","Homework","Project"]},
    {id:"c3",name:"Life Science HN",period:"1",room:"L149",teacherId:"t3",studentIds:["s1","s2"],
      weights:{Test:45,Lab:25,Homework:20,Participation:10},
      categories:["Test","Lab","Homework","Participation"]},
  ],
  assignments: [
    {id:"a1",courseId:"c1",name:"Ch 9 Test",cat:"Test",pts:100,due:"05/09/2025",published:true},
    {id:"a2",courseId:"c1",name:"HW 9.1-9.3",cat:"Homework",pts:20,due:"05/06/2025",published:true},
    {id:"a3",courseId:"c1",name:"Ch 10 Quiz",cat:"Quiz",pts:50,due:"05/15/2025",published:true},
    {id:"a4",courseId:"c1",name:"Ch 9 WS",cat:"Homework",pts:15,due:"05/02/2025",published:true},
    {id:"a5",courseId:"c2",name:"Essay: The Raven",cat:"Test",pts:100,due:"05/10/2025",published:true},
    {id:"a6",courseId:"c2",name:"Vocabulary HW",cat:"Homework",pts:20,due:"05/05/2025",published:true},
    {id:"a7",courseId:"c3",name:"Cell Lab Report",cat:"Lab",pts:50,due:"05/08/2025",published:true},
    {id:"a8",courseId:"c3",name:"Ch 12 Test",cat:"Test",pts:100,due:"05/12/2025",published:true},
  ],
  // scores: {assignmentId: {studentId: {score, comment}}}
  scores: {
    "a1":{"s1":{score:92,comment:"Great work on the proofs section!"},"s2":{score:88,comment:"Study chapter 9 review more carefully."},"s3":{score:97,comment:"Excellent!"}},
    "a2":{"s1":{score:18,comment:""},"s2":{score:16,comment:"Missing problems 4-6."},"s3":{score:20,comment:""}},
    "a3":{"s1":{score:null,comment:""},"s2":{score:null,comment:""},"s3":{score:null,comment:""}},
    "a4":{"s1":{score:15,comment:""},"s2":{score:13,comment:""},"s3":{score:15,comment:""}},
    "a5":{"s1":{score:88,comment:"Good thesis, work on transitions."},"s3":{score:94,comment:"Excellent analysis!"}},
    "a6":{"s1":{score:19,comment:""},"s3":{score:20,comment:""}},
    "a7":{"s1":{score:46,comment:"Lab procedure was well documented."},"s2":{score:42,comment:"Review safety protocols."}},
    "a8":{"s1":{score:93,comment:"Strong performance!"},"s2":{score:85,comment:"Review photosynthesis section."}},
  },
  attendance: {
    "c1":{
      "05/13/2025":{"s1":"P","s2":"P","s3":"P"},
      "05/12/2025":{"s1":"P","s2":"T","s3":"P"},
      "05/09/2025":{"s1":"P","s2":"P","s3":"A"},
      "05/08/2025":{"s1":"A","s2":"A","s3":"A"},
      "05/07/2025":{"s1":"P","s2":"P","s3":"P"},
    }
  },
  submittedGrades:{}, // {courseId_studentId: true}
  school:"Lake Braddock Middle School",
  year:"2024-2025",
});
 
/* ─── GRADE CALCULATOR ─────────────────────────────────────────── */
function calcWeightedGrade(studentId, courseId, db) {
  const course = db.courses.find(c=>c.id===courseId);
  if(!course) return {pct:0,letter:"N/A"};
  const assigns = db.assignments.filter(a=>a.courseId===courseId&&a.published);
  const weights = course.weights||{};
  // group by category
  const catData={};
  for(const cat of course.categories) catData[cat]={earned:0,possible:0};
  for(const a of assigns){
    const sc = db.scores[a.id]?.[studentId];
    if(sc&&sc.score!==null&&sc.score!==""){
      if(!catData[a.cat]) catData[a.cat]={earned:0,possible:0};
      catData[a.cat].earned+=Number(sc.score);
      catData[a.cat].possible+=a.pts;
    }
  }
  let totalWeight=0,weightedSum=0;
  for(const [cat,w] of Object.entries(weights)){
    if(catData[cat]&&catData[cat].possible>0){
      const pct=(catData[cat].earned/catData[cat].possible)*100;
      weightedSum+=pct*w;
      totalWeight+=w;
    }
  }
  if(totalWeight===0) return {pct:0,letter:"N/A"};
  const pct=Math.round((weightedSum/totalWeight)*10)/10;
  const letter=pct>=97?"A+":pct>=93?"A":pct>=90?"A-":pct>=87?"B+":pct>=83?"B":pct>=80?"B-":pct>=77?"C+":pct>=73?"C":pct>=70?"C-":pct>=67?"D+":pct>=63?"D":"F";
  return {pct,letter};
}
 
function gradeColor(g=""){
  if(!g||g==="N/A"||g==="—") return S.muted;
  if(g.startsWith("A")) return S.gradeGreen;
  if(g.startsWith("B")) return "#1155aa";
  if(g.startsWith("C")) return S.orange;
  return S.missing;
}
 
/* ─── GLOBAL CSS ───────────────────────────────────────────────── */
const G=`
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:Arial,Helvetica,sans-serif;font-size:12px;background:${S.body};color:${S.text}}
a{color:${S.link};text-decoration:none;cursor:pointer}
button{font-family:inherit;cursor:pointer;border:none;transition:opacity .15s}
button:hover{opacity:.88}
input,select,textarea{font-family:inherit;font-size:12px;box-sizing:border-box}
::-webkit-scrollbar{width:6px;height:6px}
::-webkit-scrollbar-thumb{background:#aaa;border-radius:3px}
table{border-collapse:collapse;width:100%}
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,.45);z-index:1000;display:flex;align-items:center;justify-content:center}
.modal{background:#fff;border-radius:5px;box-shadow:0 8px 32px rgba(0,0,0,.3);min-width:420px;max-width:600px;max-height:90vh;overflow-y:auto}
.toast{position:fixed;bottom:24px;right:24px;background:#333;color:#fff;padding:10px 18px;border-radius:5px;font-size:13px;z-index:2000;box-shadow:0 4px 12px rgba(0,0,0,.3);animation:fadeIn .2s}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
`;
 
/* ─── TOAST ─────────────────────────────────────────────────────── */
function Toast({msg,onClose}){
  useEffect(()=>{const t=setTimeout(onClose,3000);return()=>clearTimeout(t)},[]);
  if(!msg) return null;
  return <div className="toast">{msg}</div>;
}
 
/* ─── MODAL ─────────────────────────────────────────────────────── */
function Modal({title,children,onClose,width=480}){
  return(
    <div className="modal-overlay" onClick={e=>{if(e.target===e.currentTarget)onClose()}}>
      <div className="modal" style={{width}}>
        <div style={{background:S.navBg,color:"#fff",padding:"10px 16px",display:"flex",justifyContent:"space-between",alignItems:"center",borderRadius:"5px 5px 0 0"}}>
          <span style={{fontWeight:700,fontSize:14}}>{title}</span>
          <button onClick={onClose} style={{background:"none",color:"#fff",fontSize:18,padding:"0 4px"}}>×</button>
        </div>
        <div style={{padding:20}}>{children}</div>
      </div>
    </div>
  );
}
 
function Field({label,children,required}){
  return(
    <div style={{marginBottom:12}}>
      <label style={{display:"block",fontWeight:700,fontSize:11,color:S.grayLabel,marginBottom:3,textTransform:"uppercase",letterSpacing:.4}}>
        {label}{required&&<span style={{color:S.missing}}> *</span>}
      </label>
      {children}
    </div>
  );
}
const inp={width:"100%",border:`1px solid ${S.borderDark}`,borderRadius:3,padding:"6px 8px"};
 
/* ─── TOP BAR ────────────────────────────────────────────────────── */
function TopBar({user,onLogout}){
  const roleLabel=user.role==="admin"?"SUPER ADMIN":user.role==="teacher"?"TEACHER":"STUDENT";
  const roleBg=user.role==="admin"?"#c62828":user.role==="teacher"?S.navBg:"#2e7d32";
  return(
    <div style={{background:S.navBg,color:"#fff",padding:"0 14px",height:46,display:"flex",alignItems:"center",gap:12,boxShadow:"0 2px 4px rgba(0,0,0,.3)",position:"sticky",top:0,zIndex:200}}>
      <div style={{background:"#e8a000",borderRadius:3,padding:"3px 9px",fontWeight:900,fontSize:16,color:"#001a33",letterSpacing:1,flexShrink:0}}>S</div>
      <div style={{flex:1}}>
        <div style={{fontWeight:700,fontSize:14,lineHeight:1.1}}>Synergy <span style={{fontSize:11,fontWeight:400,opacity:.8}}>| Student Information System</span></div>
        <div style={{fontSize:10,opacity:.7}}>Lake Braddock Middle School · 2024-2025</div>
      </div>
      <span style={{fontSize:12,opacity:.9}}>Welcome, <strong>{user.name}</strong></span>
      <span style={{background:roleBg,color:"#fff",fontWeight:700,fontSize:10,padding:"2px 8px",borderRadius:2,letterSpacing:.5,border:"1px solid rgba(255,255,255,.3)"}}>{roleLabel}</span>
      <button onClick={onLogout} style={{background:"rgba(255,255,255,.15)",color:"#fff",border:"1px solid rgba(255,255,255,.3)",borderRadius:3,padding:"3px 10px",fontSize:11,fontWeight:600}}>Sign Out</button>
    </div>
  );
}
 
/* ─── LOGIN ─────────────────────────────────────────────────────── */
function Login({db,onLogin}){
  const [email,setEmail]=useState("");
  const [pass,setPass]=useState("");
  const [err,setErr]=useState("");
  const [show,setShow]=useState(false);
 
  function attempt(){
    const u=db.users.find(u=>u.email.toLowerCase()===email.trim().toLowerCase()&&u.pass===pass);
    if(!u){setErr("Invalid email or password. Please try again.");return;}
    setErr("");
    onLogin(u);
  }
 
  return(
    <div style={{minHeight:"100vh",background:`linear-gradient(160deg,#1a3a6b 0%,#2e6fad 100%)`,display:"flex",alignItems:"center",justifyContent:"center"}}>
      <div style={{background:"#fff",borderRadius:5,boxShadow:"0 4px 28px rgba(0,0,0,.45)",width:390,overflow:"hidden"}}>
        <div style={{background:S.navBg,padding:"20px 24px",display:"flex",alignItems:"center",gap:12}}>
          <div style={{background:"#e8a000",borderRadius:3,padding:"5px 12px",fontWeight:900,fontSize:20,color:"#001a33",letterSpacing:1}}>S</div>
          <div>
            <div style={{color:"#fff",fontWeight:700,fontSize:17}}>Synergy <span style={{fontWeight:400,fontSize:12,opacity:.8}}>| Student Information System</span></div>
            <div style={{color:"rgba(255,255,255,.7)",fontSize:11}}>Lake Braddock Middle School · 2024-2025</div>
          </div>
        </div>
        <div style={{padding:"22px 24px"}}>
          <Field label="Email Address" required>
            <input value={email} onChange={e=>setEmail(e.target.value)} style={inp} placeholder="you@school.edu" onKeyDown={e=>e.key==="Enter"&&attempt()}/>
          </Field>
          <Field label="Password" required>
            <div style={{position:"relative"}}>
              <input type={show?"text":"password"} value={pass} onChange={e=>setPass(e.target.value)} style={{...inp,paddingRight:60}} placeholder="••••••••" onKeyDown={e=>e.key==="Enter"&&attempt()}/>
              <button onClick={()=>setShow(s=>!s)} style={{position:"absolute",right:6,top:"50%",transform:"translateY(-50%)",background:"none",color:S.muted,fontSize:11,padding:"2px 4px"}}>{show?"Hide":"Show"}</button>
            </div>
          </Field>
          {err&&<div style={{color:S.missing,background:"#fff0f0",border:`1px solid #fcc`,borderRadius:3,padding:"7px 10px",marginBottom:12,fontSize:12}}>⚠ {err}</div>}
          <button onClick={attempt} style={{width:"100%",background:S.navBg,color:"#fff",padding:"9px",fontWeight:700,fontSize:13,borderRadius:3,marginTop:4}}>Sign In →</button>
          <div style={{marginTop:14,padding:12,background:S.sectionHdr,borderRadius:4,fontSize:11,color:S.grayLabel,lineHeight:1.6}}>
            <strong>Demo accounts:</strong><br/>
            👤 Student: jordan.m@student.fcps.edu / student123<br/>
            🍎 Teacher: lpuffer@school.edu / math1234<br/>
            🔑 Admin: history@realworld.biz / duty6556
          </div>
        </div>
      </div>
    </div>
  );
}
 
/* ══════════════════════════════════════════════════════════════════
   STUDENT PORTAL
══════════════════════════════════════════════════════════════════ */
const SNAV=[{id:"grades",label:"Grade Book"},{id:"attendance",label:"Attendance"},{id:"schedule",label:"Class Schedule"},{id:"studentinfo",label:"Student Info"},{id:"messages",label:"Messages"}];
 
function StudentPortal({user,db,onLogout}){
  const [tab,setTab]=useState("grades");
  const st=db.students.find(s=>s.id===user.studentId);
  return(
    <div style={{minHeight:"100vh",background:S.body}}>
      <TopBar user={user} onLogout={onLogout}/>
      <div style={{background:S.navBg,borderBottom:"1px solid #2a5490"}}>
        <div style={{display:"flex"}}>
          {SNAV.map(n=>(
            <button key={n.id} onClick={()=>setTab(n.id)} style={{background:tab===n.id?S.navActive:"transparent",color:"#fff",padding:"9px 14px",fontSize:12,fontWeight:tab===n.id?700:400,borderBottom:tab===n.id?"3px solid #e8a000":"3px solid transparent",whiteSpace:"nowrap"}}>
              {n.label}
            </button>
          ))}
        </div>
      </div>
      <div style={{padding:"12px 16px",maxWidth:1000,margin:"0 auto"}}>
        {tab==="grades"&&<StudentGradeBook studentId={user.studentId} db={db}/>}
        {tab==="attendance"&&<StudentAttendance studentId={user.studentId} db={db}/>}
        {tab==="schedule"&&<StudentSchedule studentId={user.studentId} db={db}/>}
        {tab==="studentinfo"&&<StudentInfoPage st={st}/>}
        {tab==="messages"&&<Placeholder t="Messages — No messages at this time."/>}
      </div>
    </div>
  );
}
 
function StudentGradeBook({studentId,db}){
  const [open,setOpen]=useState({});
  const myCourses=db.courses.filter(c=>c.studentIds.includes(studentId));
 
  return(
    <div>
      <div style={{background:S.sectionHdr,border:`1px solid ${S.sectionBdr}`,borderRadius:3,padding:"6px 10px",marginBottom:10,fontWeight:700,fontSize:13}}>
        Grade Book — {db.school} — {db.year}
      </div>
      {myCourses.map((course,ci)=>{
        const teacher=db.teachers.find(t=>t.id===course.teacherId);
        const {pct,letter}=calcWeightedGrade(studentId,course.id,db);
        const assigns=db.assignments.filter(a=>a.courseId===course.id&&a.published);
        const missing=assigns.filter(a=>{const sc=db.scores[a.id]?.[studentId];return !sc||sc.score===null||sc.score===""}).length;
        const isOpen=open[course.id]!==false;
        return(
          <div key={course.id} style={{border:`1px solid ${S.borderDark}`,borderRadius:3,marginBottom:6,background:"#fff",overflow:"hidden"}}>
            <div onClick={()=>setOpen(o=>({...o,[course.id]:!isOpen}))}
              style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",cursor:"pointer",display:"flex",alignItems:"center",gap:6,userSelect:"none"}}>
              <span style={{color:S.navBg,fontWeight:700,fontSize:11}}>{isOpen?"▾":"▸"}</span>
              <span style={{fontWeight:700,fontSize:12}}>{ci+1}: {course.name}</span>
              {teacher&&<><span style={{marginLeft:8,color:S.muted,fontSize:11}}>{teacher.name}</span><span style={{marginLeft:4,color:S.muted,fontSize:11}}>Room {course.room}</span></>}
              <span style={{marginLeft:"auto",fontWeight:700,fontSize:13,color:gradeColor(letter)}}>{letter} &nbsp;<span style={{fontSize:11,fontWeight:400,color:S.muted}}>{pct}%</span></span>
              {missing>0&&<span style={{color:S.missing,fontSize:11,marginLeft:8}}>⚠ {missing} Missing</span>}
            </div>
            {isOpen&&(
              <table>
                <colgroup><col style={{width:200}}/><col style={{width:80}}/><col style={{width:80}}/><col style={{width:80}}/><col/></colgroup>
                <thead>
                  <tr style={{background:"#eef3f9"}}>
                    <th style={{padding:"5px 10px",fontSize:11,textAlign:"left",color:S.grayLabel,fontWeight:700}}>Assignment</th>
                    <th style={{padding:"5px 8px",fontSize:11,textAlign:"center",color:S.grayLabel,fontWeight:700}}>Category</th>
                    <th style={{padding:"5px 8px",fontSize:11,textAlign:"center",color:S.grayLabel,fontWeight:700}}>Score</th>
                    <th style={{padding:"5px 8px",fontSize:11,textAlign:"center",color:S.grayLabel,fontWeight:700}}>Due</th>
                    <th style={{padding:"5px 8px",fontSize:11,textAlign:"left",color:S.grayLabel,fontWeight:700}}>Teacher Comment</th>
                  </tr>
                </thead>
                <tbody>
                  {assigns.map((a,i)=>{
                    const sc=db.scores[a.id]?.[studentId];
                    const hasScore=sc&&sc.score!==null&&sc.score!=="";
                    const pctStr=hasScore?`${Math.round((Number(sc.score)/a.pts)*1000)/10}%`:"";
                    return(
                      <tr key={a.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderTop:`1px solid ${S.border}`}}>
                        <td style={{padding:"5px 10px",fontSize:12,color:S.link}}>{a.name}</td>
                        <td style={{padding:"5px 8px",textAlign:"center"}}>
                          <span style={{background:(CAT_COLORS[a.cat]||S.muted)+"22",color:CAT_COLORS[a.cat]||S.muted,border:`1px solid ${(CAT_COLORS[a.cat]||S.muted)}55`,borderRadius:2,padding:"1px 6px",fontSize:10,fontWeight:600}}>{a.cat}</span>
                        </td>
                        <td style={{padding:"5px 8px",textAlign:"center",fontWeight:700,color:hasScore?gradeColor(Number(sc.score)/a.pts>=.9?"A":Number(sc.score)/a.pts>=.8?"B":Number(sc.score)/a.pts>=.7?"C":"D"):S.missing}}>
                          {hasScore?`${sc.score}/${a.pts}`:<span style={{fontSize:11}}>Missing</span>}
                          {hasScore&&<div style={{fontSize:10,color:S.muted,fontWeight:400}}>{pctStr}</div>}
                        </td>
                        <td style={{padding:"5px 8px",textAlign:"center",color:S.muted,fontSize:11}}>{a.due}</td>
                        <td style={{padding:"5px 8px",fontSize:11,color:sc?.comment?S.navBg:S.muted,fontStyle:sc?.comment?"normal":"italic"}}>
                          {sc?.comment||"—"}
                        </td>
                      </tr>
                    );
                  })}
                </tbody>
                <tfoot>
                  <tr style={{background:S.sectionHdr,borderTop:`2px solid ${S.sectionBdr}`}}>
                    <td colSpan={5} style={{padding:"6px 10px",fontSize:12}}>
                      <strong>Weighted Grade: <span style={{color:gradeColor(letter),fontSize:14}}>{letter}</span> ({pct}%)</strong>
                      &nbsp;|&nbsp;
                      {Object.entries(course.weights).map(([cat,w])=>(
                        <span key={cat} style={{marginRight:8,fontSize:11,color:S.grayLabel}}>{cat}: {w}%</span>
                      ))}
                    </td>
                  </tr>
                </tfoot>
              </table>
            )}
          </div>
        );
      })}
      <div style={{background:S.sectionHdr,border:`1px solid ${S.sectionBdr}`,borderRadius:3,padding:"6px 10px",marginTop:10,fontWeight:700,fontSize:12}}>Recent History</div>
    </div>
  );
}
 
function StudentAttendance({studentId,db}){
  const attDates=Object.keys(db.attendance["c1"]||{}).sort().reverse();
  const codes={"P":[S.gradeGreen,"#e8f5e9"],"A":[S.missing,"#ffebee"],"T":[S.orange,"#fff8e1"],"E":["#7b1fa2","#f3e5f5"]};
  const totals={P:0,A:0,T:0,E:0};
  attDates.forEach(d=>Object.values(db.attendance).forEach(cAtt=>{const v=cAtt[d]?.[studentId];if(v)totals[v]=(totals[v]||0)+1}));
  return(
    <div>
      <div style={{display:"flex",gap:10,marginBottom:14}}>
        {[["Present",totals.P,S.gradeGreen],["Absent",totals.A,S.missing],["Tardy",totals.T,S.orange]].map(([l,v,c])=>(
          <div key={l} style={{flex:1,background:"#fff",border:`1px solid ${S.border}`,borderRadius:3,padding:"10px 14px",textAlign:"center"}}>
            <div style={{fontSize:24,fontWeight:700,color:c}}>{v}</div>
            <div style={{fontSize:11,color:S.muted}}>{l}</div>
          </div>
        ))}
      </div>
      <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
        <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>Attendance Record</div>
        <table><thead><tr style={{background:S.headerBg}}><th style={{padding:"6px 10px",color:"#fff",fontSize:11}}>Date</th><th style={{padding:"6px 10px",color:"#fff",fontSize:11,textAlign:"center"}}>Status</th></tr></thead>
          <tbody>
            {attDates.map((d,i)=>{
              const v=db.attendance["c1"]?.[d]?.[studentId]||"P";
              const [c,bg]=codes[v]||[S.muted,"#f5f5f5"];
              return(<tr key={d} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
                <td style={{padding:"6px 10px",fontWeight:600}}>{d}</td>
                <td style={{padding:"6px 10px",textAlign:"center"}}><span style={{background:bg,color:c,border:`1px solid ${c}55`,borderRadius:3,padding:"2px 10px",fontWeight:700,fontSize:11}}>{v==="P"?"Present":v==="A"?"Absent":v==="T"?"Tardy":"Excused"}</span></td>
              </tr>);
            })}
          </tbody>
        </table>
      </div>
    </div>
  );
}
 
function StudentSchedule({studentId,db}){
  const courses=db.courses.filter(c=>c.studentIds.includes(studentId));
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>Class Schedule — 2024-2025</div>
      <table><thead><tr style={{background:S.headerBg}}>{["Period","Course","Teacher","Room","Current Grade"].map(h=><th key={h} style={{padding:"6px 10px",color:"#fff",fontSize:11,textAlign:"left"}}>{h}</th>)}</tr></thead>
        <tbody>{courses.map((c,i)=>{const t=db.teachers.find(x=>x.id===c.teacherId);const{pct,letter}=calcWeightedGrade(studentId,c.id,db);return(<tr key={c.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}><td style={{padding:"6px 10px",fontWeight:700,textAlign:"center"}}>{c.period}</td><td style={{padding:"6px 10px",color:S.link,fontWeight:600}}>{c.name}</td><td style={{padding:"6px 10px"}}>{t?.name}</td><td style={{padding:"6px 10px",color:S.muted}}>{c.room}</td><td style={{padding:"6px 10px",fontWeight:700,color:gradeColor(letter)}}>{letter} ({pct}%)</td></tr>);})}</tbody>
      </table>
    </div>
  );
}
 
function StudentInfoPage({st}){
  if(!st) return <Placeholder t="Student not found."/>;
  const fields=[["Name",`${st.first} ${st.last}`],["Grade",st.grade+"th"],["Date of Birth",st.dob],["Locker",st.locker],["Bus",st.bus],["Counselor",st.counselor],["Phone",st.phone],["Email",st.email]];
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden",maxWidth:600}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>Student Information</div>
      <div style={{padding:"14px 16px",display:"flex",gap:20,alignItems:"flex-start"}}>
        <div style={{width:80,height:96,background:S.sectionHdr,border:`1px solid ${S.sectionBdr}`,borderRadius:3,display:"flex",alignItems:"center",justifyContent:"center",flexShrink:0,fontSize:32,color:S.muted}}>👤</div>
        <div style={{display:"grid",gridTemplateColumns:"140px 1fr",gap:"7px 10px",flex:1}}>
          {fields.map(([k,v])=>[
            <span key={k+"k"} style={{fontWeight:700,fontSize:12,color:S.grayLabel}}>{k}:</span>,
            <span key={k+"v"} style={{fontSize:12}}>{v}</span>
          ])}
        </div>
      </div>
    </div>
  );
}
 
/* ══════════════════════════════════════════════════════════════════
   TEACHER PORTAL
══════════════════════════════════════════════════════════════════ */
const TNAV=[{id:"gradebook",label:"Grade Book"},{id:"attendance",label:"Attendance"},{id:"roster",label:"Student List"},{id:"assignments",label:"Assignments"},{id:"weights",label:"Grade Weights"},{id:"seating",label:"Seating Chart"},{id:"reports",label:"Reports"}];
 
function TeacherPortal({user,db,setDb,onLogout}){
  const [tab,setTab]=useState("gradebook");
  const [cls,setCls]=useState(0);
  const [toast,setToast]=useState("");
  const toast2=(msg)=>setToast(msg);
 
  const myCourses=db.courses.filter(c=>c.teacherId===user.teacherId);
 
  return(
    <div style={{minHeight:"100vh",background:S.body}}>
      <TopBar user={user} onLogout={onLogout}/>
      <div style={{background:S.navBg,borderBottom:"1px solid #2a5490"}}>
        <div style={{display:"flex"}}>{TNAV.map(n=><button key={n.id} onClick={()=>setTab(n.id)} style={{background:tab===n.id?S.navActive:"transparent",color:"#fff",padding:"9px 14px",fontSize:12,fontWeight:tab===n.id?700:400,borderBottom:tab===n.id?"3px solid #e8a000":"3px solid transparent",whiteSpace:"nowrap"}}>{n.label}</button>)}</div>
      </div>
      {/* class bar */}
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 14px",display:"flex",alignItems:"center",gap:8,flexWrap:"wrap"}}>
        <span style={{fontWeight:700,fontSize:11,color:S.grayLabel,marginRight:4}}>CLASS:</span>
        {myCourses.map((c,i)=>(
          <button key={c.id} onClick={()=>setCls(i)} style={{background:cls===i?S.navBg:"#fff",color:cls===i?"#fff":S.navBg,border:`1px solid ${S.navBg}`,borderRadius:3,padding:"4px 12px",fontSize:11,fontWeight:cls===i?700:400}}>
            Per {c.period}: {c.name}
          </button>
        ))}
      </div>
      <div style={{padding:"12px 16px",maxWidth:1100,margin:"0 auto"}}>
        {toast&&<Toast msg={toast} onClose={()=>setToast("")}/>}
        {myCourses.length===0?<Placeholder t="No classes assigned to you."/>:(()=>{
          const course=myCourses[cls];
          if(!course) return <Placeholder t="Select a class."/>;
          if(tab==="gradebook") return <TGradeBook course={course} db={db} setDb={setDb} toast={toast2}/>;
          if(tab==="attendance") return <TAttendance course={course} db={db} setDb={setDb} toast={toast2}/>;
          if(tab==="roster") return <TRoster course={course} db={db}/>;
          if(tab==="assignments") return <TAssignments course={course} db={db} setDb={setDb} toast={toast2}/>;
          if(tab==="weights") return <TWeights course={course} db={db} setDb={setDb} toast={toast2}/>;
          if(tab==="seating") return <TSeating course={course} db={db}/>;
          if(tab==="reports") return <Placeholder t="Reports — No reports generated."/>;
        })()}
      </div>
    </div>
  );
}
 
/* ─── TEACHER GRADE BOOK ─────────────────────────────────────────── */
function TGradeBook({course,db,setDb,toast}){
  const students=course.studentIds.map(id=>db.students.find(s=>s.id===id)).filter(Boolean);
  const assigns=db.assignments.filter(a=>a.courseId===course.id&&a.published);
  const [editScores,setEditScores]=useState(()=>{
    const s={};
    students.forEach(st=>{assigns.forEach(a=>{const sc=db.scores[a.id]?.[st.id];s[`${a.id}_${st.id}`]=sc?.score!==null&&sc?.score!==undefined?String(sc.score):"";});});
    return s;
  });
  const [editComments,setEditComments]=useState(()=>{
    const c={};
    students.forEach(st=>{assigns.forEach(a=>{const sc=db.scores[a.id]?.[st.id];c[`${a.id}_${st.id}`]=sc?.comment||"";});});
    return c;
  });
  const [commentCell,setCommentCell]=useState(null); // {aId,sId}
  const [submitted,setSubmitted]=useState(false);
  const [dirty,setDirty]=useState(false);
 
  function handleScore(aId,sId,val){
    setEditScores(s=>({...s,[`${aId}_${sId}`]:val}));
    setDirty(true);
  }
  function handleComment(aId,sId,val){
    setEditComments(c=>({...c,[`${aId}_${sId}`]:val}));
    setDirty(true);
  }
  function saveAll(){
    setDb(prev=>{
      const newScores={...prev.scores};
      students.forEach(st=>{
        assigns.forEach(a=>{
          const key=`${a.id}_${st.id}`;
          const raw=editScores[key];
          const comment=editComments[key]||"";
          const score=raw===""?null:isNaN(Number(raw))?null:Number(raw);
          if(!newScores[a.id]) newScores[a.id]={};
          newScores[a.id][st.id]={score,comment};
        });
      });
      return {...prev,scores:newScores};
    });
    setDirty(false);
    setSubmitted(true);
    toast("✅ Grades saved and submitted successfully!");
  }
 
  const avg=(vals)=>{const v=vals.filter(x=>x!==null&&x!==""&&!isNaN(Number(x)));return v.length?Math.round(v.reduce((a,b)=>a+Number(b),0)/v.length*10)/10:null};
 
  return(
    <div>
      <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
        <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",alignItems:"center",justifyContent:"space-between"}}>
          <span style={{fontWeight:700,fontSize:12}}>Grade Book — {course.name} — Period {course.period}</span>
          <div style={{display:"flex",gap:6,alignItems:"center"}}>
            {dirty&&<span style={{color:S.orange,fontSize:11,fontWeight:700}}>● Unsaved changes</span>}
            {submitted&&!dirty&&<span style={{color:S.gradeGreen,fontSize:11,fontWeight:700}}>✓ Grades submitted</span>}
          </div>
        </div>
        <div style={{overflowX:"auto"}}>
          <table>
            <thead>
              <tr style={{background:S.headerBg}}>
                <th style={{padding:"6px 10px",color:"#fff",textAlign:"left",minWidth:160,fontSize:11,position:"sticky",left:0,background:S.headerBg}}>Student</th>
                <th style={{padding:"6px 10px",color:"#fff",textAlign:"center",width:80,fontSize:11}}>Grade</th>
                {assigns.map(a=>(
                  <th key={a.id} style={{padding:"6px 8px",color:"#fff",textAlign:"center",minWidth:90,fontSize:11}}>
                    <div style={{fontWeight:700}}>{a.name}</div>
                    <div style={{fontSize:10,opacity:.8,fontWeight:400}}>
                      <span style={{background:(CAT_COLORS[a.cat]||"#555")+"55",borderRadius:2,padding:"0 3px"}}>{a.cat}</span> /{a.pts}
                    </div>
                    <div style={{fontSize:10,opacity:.7,fontWeight:400}}>Due {a.due}</div>
                  </th>
                ))}
              </tr>
            </thead>
            <tbody>
              {students.map((st,si)=>{
                const {pct,letter}=calcWeightedGrade(st.id,course.id,{...db,scores:(() => {
                  const ns={...db.scores};
                  assigns.forEach(a=>{
                    const key=`${a.id}_${st.id}`;const raw=editScores[key];
                    if(!ns[a.id])ns[a.id]={};
                    ns[a.id][st.id]={score:raw===""?null:isNaN(Number(raw))?null:Number(raw),comment:editComments[key]||""};
                  });
                  return ns;
                })()});
                return(
                  <tr key={st.id} style={{background:si%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
                    <td style={{padding:"5px 10px",fontWeight:600,fontSize:12,color:S.link,position:"sticky",left:0,background:si%2===0?S.rowOdd:S.rowEven}}>{st.last}, {st.first}</td>
                    <td style={{padding:"5px",textAlign:"center"}}>
                      <span style={{fontWeight:700,fontSize:13,color:gradeColor(letter)}}>{letter}</span>
                      <div style={{fontSize:10,color:S.muted}}>{pct}%</div>
                    </td>
                    {assigns.map(a=>{
                      const key=`${a.id}_${st.id}`;
                      const isActive=commentCell&&commentCell.aId===a.id&&commentCell.sId===st.id;
                      return(
                        <td key={a.id} style={{padding:"3px 5px",textAlign:"center",position:"relative"}}>
                          <input value={editScores[key]??""}
                            onChange={e=>handleScore(a.id,st.id,e.target.value)}
                            style={{width:52,textAlign:"center",border:`1px solid ${S.border}`,borderRadius:2,padding:"3px 2px",fontSize:12,background:editScores[key]===""?"#fff8e1":"#fff"}}
                            placeholder="—"/>
                          <button onClick={()=>setCommentCell(isActive?null:{aId:a.id,sId:st.id})}
                            title={editComments[key]?"Edit comment":"Add comment"}
                            style={{marginLeft:2,background:"none",fontSize:13,padding:0,opacity:editComments[key]?1:.35}}>
                            💬
                          </button>
                          {isActive&&(
                            <div style={{position:"absolute",zIndex:100,background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:4,padding:8,boxShadow:"0 4px 12px rgba(0,0,0,.2)",width:220,left:"50%",transform:"translateX(-50%)",top:"100%"}}>
                              <div style={{fontWeight:700,fontSize:11,marginBottom:4,color:S.navBg}}>Comment for {st.first}:</div>
                              <textarea rows={3} value={editComments[key]||""} onChange={e=>handleComment(a.id,st.id,e.target.value)}
                                style={{width:"100%",border:`1px solid ${S.border}`,borderRadius:3,padding:"4px 6px",fontSize:11,resize:"vertical"}}
                                placeholder="Type teacher comment visible to student..."/>
                              <div style={{display:"flex",gap:6,marginTop:6}}>
                                <button onClick={()=>setCommentCell(null)} style={{flex:1,background:S.gradeGreen,color:"#fff",borderRadius:3,padding:"4px",fontSize:11,fontWeight:700}}>Save</button>
                                <button onClick={()=>{handleComment(a.id,st.id,"");setCommentCell(null);}} style={{background:"#eee",color:S.muted,borderRadius:3,padding:"4px 8px",fontSize:11}}>Clear</button>
                              </div>
                            </div>
                          )}
                        </td>
                      );
                    })}
                  </tr>
                );
              })}
              {/* class avg */}
              <tr style={{background:S.sectionHdr,borderTop:`2px solid ${S.sectionBdr}`}}>
                <td style={{padding:"5px 10px",fontWeight:700,fontSize:12,position:"sticky",left:0,background:S.sectionHdr}}>Class Average</td>
                <td/>
                {assigns.map(a=>{
                  const vals=students.map(st=>editScores[`${a.id}_${st.id}`]);
                  const v=avg(vals);
                  return<td key={a.id} style={{padding:"5px",textAlign:"center",fontWeight:700,color:v?gradeColor(v>=90?"A":v>=80?"B":v>=70?"C":"D"):S.muted}}>{v??'—'}</td>;
                })}
              </tr>
            </tbody>
          </table>
        </div>
        {/* SUBMIT BUTTON */}
        <div style={{padding:"12px 14px",borderTop:`2px solid ${S.sectionBdr}`,background:S.sectionHdr,display:"flex",alignItems:"center",gap:12}}>
          <button onClick={saveAll}
            style={{background:S.gradeGreen,color:"#fff",padding:"9px 28px",fontWeight:700,fontSize:13,borderRadius:4,boxShadow:"0 2px 6px rgba(0,100,0,.25)"}}>
            💾 Submit Grades
          </button>
          {dirty&&<span style={{fontSize:12,color:S.orange,fontWeight:700}}>You have unsaved changes — click Submit Grades to save.</span>}
          {submitted&&!dirty&&<span style={{fontSize:12,color:S.gradeGreen,fontWeight:700}}>✓ All grades submitted successfully. Students can now view their grades.</span>}
          <span style={{marginLeft:"auto",fontSize:11,color:S.muted}}>💬 = teacher comment (visible to student)</span>
        </div>
      </div>
    </div>
  );
}
 
/* ─── TEACHER WEIGHTS ────────────────────────────────────────────── */
function TWeights({course,db,setDb,toast}){
  const [weights,setWeights]=useState({...course.weights});
  const total=Object.values(weights).reduce((a,b)=>a+Number(b||0),0);
  const valid=Math.round(total)===100;
 
  function save(){
    if(!valid){toast("⚠ Weights must add up to 100%.");return;}
    setDb(prev=>({...prev,courses:prev.courses.map(c=>c.id===course.id?{...c,weights:{...weights}}:c)}));
    toast("✅ Grade weights updated!");
  }
 
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden",maxWidth:500}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>
        Grade Category Weights — {course.name}
      </div>
      <div style={{padding:16}}>
        <p style={{fontSize:12,color:S.muted,marginBottom:14}}>Set the percentage weight for each grading category. Weights must total 100%.</p>
        {course.categories.map(cat=>(
          <div key={cat} style={{display:"flex",alignItems:"center",gap:10,marginBottom:10}}>
            <span style={{width:120,fontWeight:700,fontSize:12,color:CAT_COLORS[cat]||S.text}}>{cat}</span>
            <input type="number" min={0} max={100} value={weights[cat]??0} onChange={e=>setWeights(w=>({...w,[cat]:Number(e.target.value)}))}
              style={{width:70,border:`1px solid ${S.borderDark}`,borderRadius:3,padding:"5px 8px",textAlign:"center",fontWeight:700}}/>
            <span style={{fontSize:12,color:S.muted}}>%</span>
            <div style={{flex:1,background:"#eee",borderRadius:3,height:8,overflow:"hidden"}}>
              <div style={{width:`${Math.min(weights[cat]||0,100)}%`,background:CAT_COLORS[cat]||S.navBg,height:"100%",transition:"width .3s"}}/>
            </div>
          </div>
        ))}
        <div style={{display:"flex",alignItems:"center",gap:12,marginTop:16,paddingTop:12,borderTop:`1px solid ${S.border}`}}>
          <span style={{fontWeight:700,fontSize:13,color:valid?S.gradeGreen:S.missing}}>Total: {total}% {valid?"✓":"⚠ Must equal 100%"}</span>
          <button onClick={save} style={{marginLeft:"auto",background:valid?S.gradeGreen:"#999",color:"#fff",padding:"7px 20px",borderRadius:3,fontWeight:700,fontSize:12}}>Save Weights</button>
        </div>
      </div>
    </div>
  );
}
 
/* ─── TEACHER ATTENDANCE ─────────────────────────────────────────── */
function TAttendance({course,db,setDb,toast}){
  const students=course.studentIds.map(id=>db.students.find(s=>s.id===id)).filter(Boolean);
  const today=new Date().toLocaleDateString("en-US",{month:"2-digit",day:"2-digit",year:"numeric"});
  const existing=db.attendance[course.id]?.[today]||{};
  const [att,setAtt]=useState(()=>Object.fromEntries(students.map(s=>[s.id,existing[s.id]||"P"])));
  const opts=["P","A","T","E"];
  const colors={P:S.gradeGreen,A:S.missing,T:S.orange,E:"#7b1fa2"};
  const present=Object.values(att).filter(v=>v==="P").length;
 
  function save(){
    setDb(prev=>({...prev,attendance:{...prev.attendance,[course.id]:{...(prev.attendance[course.id]||{}),[today]:{...att}}}}));
    toast("✅ Attendance saved for "+today);
  }
 
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",alignItems:"center",justifyContent:"space-between"}}>
        <span style={{fontWeight:700,fontSize:12}}>Attendance — {course.name} — {today}</span>
        <div style={{display:"flex",gap:8,alignItems:"center"}}>
          <span style={{fontSize:11,color:S.muted}}>{present}/{students.length} Present</span>
          <button onClick={save} style={{background:S.gradeGreen,color:"#fff",borderRadius:3,padding:"5px 14px",fontSize:11,fontWeight:700}}>💾 Save Attendance</button>
        </div>
      </div>
      <table>
        <thead><tr style={{background:S.headerBg}}>
          <th style={{padding:"6px 10px",color:"#fff",fontSize:11,width:30}}>#</th>
          <th style={{padding:"6px 10px",color:"#fff",fontSize:11}}>Student</th>
          {opts.map(o=><th key={o} style={{padding:"6px 10px",color:"#fff",textAlign:"center",width:50,fontSize:11}}>{o}</th>)}
          <th style={{padding:"6px 10px",color:"#fff",fontSize:11}}>Note</th>
        </tr></thead>
        <tbody>
          {students.map((s,i)=>(
            <tr key={s.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
              <td style={{padding:"5px 10px",color:S.muted,fontSize:11}}>{i+1}</td>
              <td style={{padding:"5px 10px",fontWeight:600,fontSize:12}}>{s.last}, {s.first}</td>
              {opts.map(o=>(
                <td key={o} style={{padding:"5px",textAlign:"center"}}>
                  <label style={{cursor:"pointer",display:"flex",alignItems:"center",justifyContent:"center"}}>
                    <input type="radio" name={`att_${s.id}`} checked={att[s.id]===o} onChange={()=>setAtt(a=>({...a,[s.id]:o}))} style={{width:15,height:15,accentColor:colors[o]}}/>
                  </label>
                </td>
              ))}
              <td style={{padding:"5px 8px"}}><input style={{width:150,border:`1px solid ${S.border}`,borderRadius:2,padding:"2px 5px",fontSize:11}} placeholder="Optional note..."/></td>
            </tr>
          ))}
        </tbody>
      </table>
      <div style={{padding:"7px 10px",borderTop:`1px solid ${S.border}`,fontSize:11,color:S.muted}}>
        P = Present &nbsp; A = Absent &nbsp; T = Tardy &nbsp; E = Excused
      </div>
    </div>
  );
}
 
/* ─── TEACHER ASSIGNMENTS ────────────────────────────────────────── */
function TAssignments({course,db,setDb,toast}){
  const assigns=db.assignments.filter(a=>a.courseId===course.id);
  const [showModal,setShowModal]=useState(false);
  const [editA,setEditA]=useState(null);
  const [form,setForm]=useState({name:"",cat:course.categories[0]||"Test",pts:"100",due:"",desc:""});
  const [formErr,setFormErr]=useState("");
 
  function openNew(){setForm({name:"",cat:course.categories[0]||"Test",pts:"100",due:"",desc:""});setEditA(null);setFormErr("");setShowModal(true);}
  function openEdit(a){setForm({name:a.name,cat:a.cat,pts:String(a.pts),due:a.due,desc:a.desc||""});setEditA(a);setFormErr("");setShowModal(true);}
 
  function submit(){
    if(!form.name.trim()){setFormErr("Assignment name is required.");return;}
    if(!form.due){setFormErr("Due date is required.");return;}
    const pts=Number(form.pts);
    if(!pts||pts<1){setFormErr("Points must be a positive number.");return;}
    setFormErr("");
    if(editA){
      setDb(prev=>({...prev,assignments:prev.assignments.map(a=>a.id===editA.id?{...a,...form,pts}:a)}));
      toast("✅ Assignment updated!");
    } else {
      const newA={id:"a"+Date.now(),courseId:course.id,...form,pts,published:true};
      setDb(prev=>({...prev,assignments:[...prev.assignments,newA],scores:{...prev.scores,[newA.id]:{}}}));
      toast("✅ Assignment created!");
    }
    setShowModal(false);
  }
 
  function deleteA(a){
    if(!window.confirm(`Delete "${a.name}"? This will remove all scores.`)) return;
    setDb(prev=>{const ns={...prev.scores};delete ns[a.id];return{...prev,assignments:prev.assignments.filter(x=>x.id!==a.id),scores:ns};});
    toast("🗑 Assignment deleted.");
  }
 
  const students=course.studentIds.map(id=>db.students.find(s=>s.id===id)).filter(Boolean);
  const avg=(aId)=>{const vals=students.map(s=>db.scores[aId]?.[s.id]?.score).filter(x=>x!==null&&x!==undefined&&x!=="");return vals.length?Math.round(vals.reduce((a,b)=>a+Number(b),0)/vals.length*10)/10:null;};
 
  return(
    <div>
      {showModal&&(
        <Modal title={editA?"Edit Assignment":"Create New Assignment"} onClose={()=>setShowModal(false)}>
          <Field label="Assignment Name" required><input value={form.name} onChange={e=>setForm(f=>({...f,name:e.target.value}))} style={inp} placeholder="e.g. Chapter 10 Test"/></Field>
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
            <Field label="Category" required>
              <select value={form.cat} onChange={e=>setForm(f=>({...f,cat:e.target.value}))} style={inp}>
                {course.categories.map(c=><option key={c} value={c}>{c}</option>)}
              </select>
            </Field>
            <Field label="Total Points" required><input type="number" min={1} value={form.pts} onChange={e=>setForm(f=>({...f,pts:e.target.value}))} style={inp}/></Field>
          </div>
          <Field label="Due Date" required><input type="date" value={form.due} onChange={e=>setForm(f=>({...f,due:e.target.value}))} style={inp}/></Field>
          <Field label="Description (optional)"><textarea rows={3} value={form.desc} onChange={e=>setForm(f=>({...f,desc:e.target.value}))} style={{...inp,resize:"vertical"}} placeholder="Instructions visible to students..."/></Field>
          {formErr&&<div style={{color:S.missing,background:"#fff0f0",border:`1px solid #fcc`,borderRadius:3,padding:"6px 10px",marginBottom:10,fontSize:12}}>⚠ {formErr}</div>}
          <div style={{display:"flex",gap:8,justifyContent:"flex-end",marginTop:4}}>
            <button onClick={()=>setShowModal(false)} style={{background:"#eee",color:S.text,borderRadius:3,padding:"7px 18px",fontSize:12}}>Cancel</button>
            <button onClick={submit} style={{background:S.gradeGreen,color:"#fff",borderRadius:3,padding:"7px 18px",fontSize:12,fontWeight:700}}>{editA?"Save Changes":"Create Assignment"}</button>
          </div>
        </Modal>
      )}
      <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
        <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",alignItems:"center",justifyContent:"space-between"}}>
          <span style={{fontWeight:700,fontSize:12}}>Assignments — {course.name} ({assigns.length})</span>
          <button onClick={openNew} style={{background:S.navBg,color:"#fff",borderRadius:3,padding:"5px 14px",fontSize:11,fontWeight:700}}>+ New Assignment</button>
        </div>
        {assigns.length===0?<div style={{padding:20,color:S.muted,textAlign:"center"}}>No assignments yet. Click "+ New Assignment" to create one.</div>:(
          <table>
            <thead><tr style={{background:S.headerBg}}>{["Assignment","Category","Points","Due Date","Class Avg","Status","Actions"].map(h=><th key={h} style={{padding:"6px 10px",color:"#fff",fontSize:11,textAlign:"left"}}>{h}</th>)}</tr></thead>
            <tbody>
              {assigns.map((a,i)=>{
                const v=avg(a.id);
                return(
                  <tr key={a.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
                    <td style={{padding:"6px 10px",fontWeight:600,color:S.link,fontSize:12}}>{a.name}{a.desc&&<div style={{fontSize:10,color:S.muted,fontStyle:"italic",fontWeight:400}}>{a.desc}</div>}</td>
                    <td style={{padding:"6px 10px"}}><span style={{background:(CAT_COLORS[a.cat]||"#555")+"22",color:CAT_COLORS[a.cat]||"#555",border:`1px solid ${(CAT_COLORS[a.cat]||"#555")}55`,borderRadius:2,padding:"1px 7px",fontSize:11,fontWeight:600}}>{a.cat}</span></td>
                    <td style={{padding:"6px 10px",textAlign:"center",fontWeight:600}}>{a.pts}</td>
                    <td style={{padding:"6px 10px",color:S.muted}}>{a.due}</td>
                    <td style={{padding:"6px 10px",textAlign:"center",fontWeight:700,color:v?gradeColor(v>=90?"A":v>=80?"B":v>=70?"C":"D"):S.muted}}>{v??'—'}</td>
                    <td style={{padding:"6px 10px"}}><span style={{color:v?S.gradeGreen:S.orange,fontWeight:700,fontSize:11}}>{v?"Graded":"Pending"}</span></td>
                    <td style={{padding:"6px 8px",display:"flex",gap:4}}>
                      <button onClick={()=>openEdit(a)} style={{background:S.sectionHdr,color:S.navBg,border:`1px solid ${S.sectionBdr}`,borderRadius:2,padding:"2px 8px",fontSize:11}}>Edit</button>
                      <button onClick={()=>deleteA(a)} style={{background:"#ffebee",color:S.missing,border:`1px solid ${S.missing}44`,borderRadius:2,padding:"2px 8px",fontSize:11}}>Del</button>
                    </td>
                  </tr>
                );
              })}
            </tbody>
          </table>
        )}
      </div>
    </div>
  );
}
 
/* ─── TEACHER ROSTER ─────────────────────────────────────────────── */
function TRoster({course,db}){
  const students=course.studentIds.map(id=>db.students.find(s=>s.id===id)).filter(Boolean);
  const [q,setQ]=useState("");
  const filtered=students.filter(s=>`${s.first} ${s.last}`.toLowerCase().includes(q.toLowerCase()));
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",alignItems:"center",justifyContent:"space-between"}}>
        <span style={{fontWeight:700,fontSize:12}}>Student List — {course.name} ({students.length} students)</span>
        <input value={q} onChange={e=>setQ(e.target.value)} placeholder="Search students..." style={{border:`1px solid ${S.border}`,borderRadius:3,padding:"3px 7px",fontSize:11,width:150}}/>
      </div>
      <table><thead><tr style={{background:S.headerBg}}>{["#","Last Name","First Name","Grade","Current %","Letter","Missing"].map(h=><th key={h} style={{padding:"6px 8px",color:"#fff",fontSize:11,textAlign:"left"}}>{h}</th>)}</tr></thead>
        <tbody>{filtered.map((s,i)=>{
          const{pct,letter}=calcWeightedGrade(s.id,course.id,db);
          const missing=db.assignments.filter(a=>a.courseId===course.id&&a.published).filter(a=>{const sc=db.scores[a.id]?.[s.id];return !sc||sc.score===null||sc.score===""}).length;
          return(<tr key={s.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
            <td style={{padding:"5px 8px",color:S.muted,fontSize:11}}>{i+1}</td>
            <td style={{padding:"5px 8px",fontWeight:600,color:S.link,fontSize:12}}>{s.last}</td>
            <td style={{padding:"5px 8px",fontSize:12}}>{s.first}</td>
            <td style={{padding:"5px 8px",textAlign:"center"}}>{s.grade}</td>
            <td style={{padding:"5px 8px",textAlign:"center",fontWeight:700,color:gradeColor(letter)}}>{pct}%</td>
            <td style={{padding:"5px 8px",textAlign:"center",fontWeight:700,color:gradeColor(letter),fontSize:14}}>{letter}</td>
            <td style={{padding:"5px 8px",textAlign:"center"}}>{missing>0?<span style={{color:S.missing,fontWeight:700,fontSize:11}}>⚠ {missing}</span>:<span style={{color:S.gradeGreen}}>✓</span>}</td>
          </tr>);
        })}</tbody>
      </table>
    </div>
  );
}
 
/* ─── TEACHER SEATING ────────────────────────────────────────────── */
function TSeating({course,db}){
  const students=course.studentIds.map(id=>db.students.find(s=>s.id===id)).filter(Boolean);
  const cols=4;const rows=Math.ceil(students.length/cols);
  const grid=Array.from({length:rows},(_,r)=>students.slice(r*cols,(r+1)*cols));
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>Seating Chart — {course.name} — Room {course.room}</div>
      <div style={{background:"#e8f0fb",borderBottom:`1px solid ${S.sectionBdr}`,padding:"6px",textAlign:"center",fontSize:11,fontWeight:700,letterSpacing:1,color:S.navBg}}>━━━  WHITEBOARD / FRONT OF ROOM  ━━━</div>
      <div style={{padding:16,display:"flex",flexDirection:"column",gap:10}}>
        {grid.map((row,ri)=>(
          <div key={ri} style={{display:"flex",gap:10}}>
            {row.map((s,ci)=>{
              const{letter}=calcWeightedGrade(s.id,course.id,db);
              return(
                <div key={s.id} style={{width:130,height:64,borderRadius:4,border:`2px solid ${S.sectionBdr}`,background:S.rowOdd,display:"flex",flexDirection:"column",alignItems:"center",justifyContent:"center",fontSize:11,padding:4,textAlign:"center"}}>
                  <span style={{fontWeight:700,color:S.navBg,fontSize:12}}>{s.first}</span>
                  <span style={{color:S.muted,fontSize:10}}>{s.last}</span>
                  <span style={{fontWeight:700,fontSize:12,color:gradeColor(letter)}}>{letter}</span>
                </div>
              );
            })}
          </div>
        ))}
      </div>
    </div>
  );
}
 
/* ══════════════════════════════════════════════════════════════════
   SUPER ADMIN PORTAL
══════════════════════════════════════════════════════════════════ */
const ANAV=[{id:"dashboard",label:"Dashboard"},{id:"courses",label:"Courses"},{id:"teachers",label:"Teachers"},{id:"students",label:"Students"},{id:"users",label:"User Accounts"}];
 
function AdminPortal({user,db,setDb,onLogout}){
  const [tab,setTab]=useState("dashboard");
  const [toast,setToast]=useState("");
  const toast2=msg=>setToast(msg);
  return(
    <div style={{minHeight:"100vh",background:S.body}}>
      <TopBar user={user} onLogout={onLogout}/>
      <div style={{background:"#8b0000",borderBottom:"1px solid #600"}}>
        <div style={{display:"flex"}}>{ANAV.map(n=><button key={n.id} onClick={()=>setTab(n.id)} style={{background:tab===n.id?"#600":"transparent",color:"#fff",padding:"9px 16px",fontSize:12,fontWeight:tab===n.id?700:400,borderBottom:tab===n.id?"3px solid #e8a000":"3px solid transparent",whiteSpace:"nowrap"}}>{n.label}</button>)}</div>
      </div>
      <div style={{padding:"12px 16px",maxWidth:1100,margin:"0 auto"}}>
        {toast&&<Toast msg={toast} onClose={()=>setToast("")}/>}
        {tab==="dashboard"&&<AdminDashboard db={db}/>}
        {tab==="courses"&&<AdminCourses db={db} setDb={setDb} toast={toast2}/>}
        {tab==="teachers"&&<AdminTeachers db={db} setDb={setDb} toast={toast2}/>}
        {tab==="students"&&<AdminStudents db={db} setDb={setDb} toast={toast2}/>}
        {tab==="users"&&<AdminUsers db={db} setDb={setDb} toast={toast2}/>}
      </div>
    </div>
  );
}
 
function AdminDashboard({db}){
  const stats=[["Total Students",db.students.length,"#2e7d32"],["Total Teachers",db.teachers.length,S.navBg],["Total Courses",db.courses.length,"#e07800"],["Total Assignments",db.assignments.length,"#6a1b9a"]];
  return(
    <div>
      <div style={{background:"#fff2f2",border:"1px solid #f00",borderRadius:4,padding:"10px 14px",marginBottom:16,fontSize:13,fontWeight:700,color:"#8b0000"}}>
        🔑 Super Admin Panel — Full system access for history@realworld.biz
      </div>
      <div style={{display:"grid",gridTemplateColumns:"repeat(4,1fr)",gap:12,marginBottom:20}}>
        {stats.map(([l,v,c])=>(
          <div key={l} style={{background:"#fff",border:`1px solid ${S.border}`,borderRadius:4,padding:"16px",textAlign:"center"}}>
            <div style={{fontSize:28,fontWeight:800,color:c}}>{v}</div>
            <div style={{fontSize:12,color:S.muted}}>{l}</div>
          </div>
        ))}
      </div>
      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:16}}>
        <div style={{background:"#fff",border:`1px solid ${S.border}`,borderRadius:4,overflow:"hidden"}}>
          <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>All Courses</div>
          <table><thead><tr style={{background:S.headerBg}}>{["Course","Period","Teacher","Students"].map(h=><th key={h} style={{padding:"5px 8px",color:"#fff",fontSize:11}}>{h}</th>)}</tr></thead>
            <tbody>{db.courses.map((c,i)=>{const t=db.teachers.find(x=>x.id===c.teacherId);return(<tr key={c.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}><td style={{padding:"5px 8px",fontWeight:600,fontSize:11}}>{c.name}</td><td style={{padding:"5px 8px",textAlign:"center",fontSize:11}}>{c.period}</td><td style={{padding:"5px 8px",fontSize:11}}>{t?.name||"Unassigned"}</td><td style={{padding:"5px 8px",textAlign:"center",fontSize:11}}>{c.studentIds.length}</td></tr>);})}</tbody>
          </table>
        </div>
        <div style={{background:"#fff",border:`1px solid ${S.border}`,borderRadius:4,overflow:"hidden"}}>
          <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>All Teachers</div>
          <table><thead><tr style={{background:S.headerBg}}>{["Name","Subject","Room","Email"].map(h=><th key={h} style={{padding:"5px 8px",color:"#fff",fontSize:11}}>{h}</th>)}</tr></thead>
            <tbody>{db.teachers.map((t,i)=><tr key={t.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}><td style={{padding:"5px 8px",fontWeight:600,fontSize:11}}>{t.name}</td><td style={{padding:"5px 8px",fontSize:11}}>{t.subject}</td><td style={{padding:"5px 8px",fontSize:11}}>{t.room}</td><td style={{padding:"5px 8px",fontSize:11,color:S.link}}>{t.email}</td></tr>)}</tbody>
          </table>
        </div>
      </div>
    </div>
  );
}
 
function AdminCourses({db,setDb,toast}){
  const [showModal,setShowModal]=useState(false);
  const [form,setForm]=useState({name:"",period:"1",room:"",teacherId:"",categories:"Test,Quiz,Homework,Project",weights:"Test:40,Quiz:25,Homework:25,Project:10"});
  const [err,setErr]=useState("");
 
  function submit(){
    if(!form.name.trim()||!form.room.trim()||!form.teacherId){setErr("Name, Room, and Teacher are required.");return;}
    const cats=form.categories.split(",").map(s=>s.trim()).filter(Boolean);
    const wPairs=form.weights.split(",").map(s=>s.trim()).filter(Boolean);
    const weights={};wPairs.forEach(p=>{const[k,v]=p.split(":");if(k&&v)weights[k.trim()]=Number(v.trim())||0;});
    const newC={id:"c"+Date.now(),name:form.name,period:form.period,room:form.room,teacherId:form.teacherId,studentIds:[],weights,categories:cats};
    setDb(prev=>({...prev,courses:[...prev.courses,newC]}));
    toast("✅ Course '"+form.name+"' created!");setShowModal(false);setErr("");
  }
 
  function del(c){
    if(!window.confirm(`Delete course "${c.name}"? This cannot be undone.`))return;
    setDb(prev=>({...prev,courses:prev.courses.filter(x=>x.id!==c.id)}));
    toast("🗑 Course deleted.");
  }
 
  return(
    <div>
      {showModal&&(
        <Modal title="Create New Course" onClose={()=>setShowModal(false)} width={520}>
          <Field label="Course Name" required><input value={form.name} onChange={e=>setForm(f=>({...f,name:e.target.value}))} style={inp} placeholder="e.g. Mathematics 8"/></Field>
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
            <Field label="Period" required><input value={form.period} onChange={e=>setForm(f=>({...f,period:e.target.value}))} style={inp}/></Field>
            <Field label="Room" required><input value={form.room} onChange={e=>setForm(f=>({...f,room:e.target.value}))} style={inp}/></Field>
          </div>
          <Field label="Assigned Teacher" required>
            <select value={form.teacherId} onChange={e=>setForm(f=>({...f,teacherId:e.target.value}))} style={inp}>
              <option value="">— Select Teacher —</option>
              {db.teachers.map(t=><option key={t.id} value={t.id}>{t.name} ({t.subject})</option>)}
            </select>
          </Field>
          <Field label="Grade Categories (comma-separated)"><input value={form.categories} onChange={e=>setForm(f=>({...f,categories:e.target.value}))} style={inp} placeholder="Test,Quiz,Homework"/></Field>
          <Field label="Category Weights (Category:Weight, comma-separated)"><input value={form.weights} onChange={e=>setForm(f=>({...f,weights:e.target.value}))} style={inp} placeholder="Test:40,Quiz:25,Homework:35"/></Field>
          {err&&<div style={{color:S.missing,background:"#fff0f0",borderRadius:3,padding:"6px",marginBottom:8,fontSize:12}}>⚠ {err}</div>}
          <div style={{display:"flex",gap:8,justifyContent:"flex-end",marginTop:8}}>
            <button onClick={()=>setShowModal(false)} style={{background:"#eee",borderRadius:3,padding:"7px 16px",fontSize:12}}>Cancel</button>
            <button onClick={submit} style={{background:"#8b0000",color:"#fff",borderRadius:3,padding:"7px 16px",fontSize:12,fontWeight:700}}>Create Course</button>
          </div>
        </Modal>
      )}
      <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
        <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",justifyContent:"space-between",alignItems:"center"}}>
          <span style={{fontWeight:700,fontSize:12}}>All Courses ({db.courses.length})</span>
          <button onClick={()=>setShowModal(true)} style={{background:"#8b0000",color:"#fff",borderRadius:3,padding:"5px 14px",fontSize:11,fontWeight:700}}>+ Create Course</button>
        </div>
        <table><thead><tr style={{background:S.headerBg}}>{["Course","Period","Room","Teacher","Students","Categories","Action"].map(h=><th key={h} style={{padding:"6px 10px",color:"#fff",fontSize:11}}>{h}</th>)}</tr></thead>
          <tbody>{db.courses.map((c,i)=>{const t=db.teachers.find(x=>x.id===c.teacherId);return(<tr key={c.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
            <td style={{padding:"6px 10px",fontWeight:700,fontSize:12}}>{c.name}</td>
            <td style={{padding:"6px 10px",textAlign:"center"}}>{c.period}</td>
            <td style={{padding:"6px 10px"}}>{c.room}</td>
            <td style={{padding:"6px 10px",color:S.link}}>{t?.name||<span style={{color:S.missing}}>Unassigned</span>}</td>
            <td style={{padding:"6px 10px",textAlign:"center"}}>{c.studentIds.length}</td>
            <td style={{padding:"6px 10px",fontSize:11,color:S.muted}}>{c.categories?.join(", ")}</td>
            <td style={{padding:"6px 8px"}}><button onClick={()=>del(c)} style={{background:"#ffebee",color:S.missing,border:`1px solid ${S.missing}44`,borderRadius:2,padding:"2px 8px",fontSize:11}}>Delete</button></td>
          </tr>);})}</tbody>
        </table>
      </div>
    </div>
  );
}
 
function AdminTeachers({db,setDb,toast}){
  const [showModal,setShowModal]=useState(false);
  const [form,setForm]=useState({name:"",email:"",room:"",subject:"",pass:""});
  const [err,setErr]=useState("");
 
  function submit(){
    if(!form.name.trim()||!form.email.trim()||!form.pass.trim()){setErr("Name, email, and password are required.");return;}
    if(db.users.find(u=>u.email.toLowerCase()===form.email.toLowerCase())){setErr("Email already in use.");return;}
    const tId="t"+Date.now();const uId="u"+Date.now();
    const newTeacher={id:tId,name:form.name,email:form.email,room:form.room,subject:form.subject};
    const newUser={id:uId,email:form.email,pass:form.pass,role:"teacher",name:form.name,teacherId:tId};
    setDb(prev=>({...prev,teachers:[...prev.teachers,newTeacher],users:[...prev.users,newUser]}));
    toast("✅ Teacher '"+form.name+"' created!");setShowModal(false);setErr("");setForm({name:"",email:"",room:"",subject:"",pass:""});
  }
 
  function del(t){
    if(!window.confirm(`Delete teacher "${t.name}"?`))return;
    setDb(prev=>({...prev,teachers:prev.teachers.filter(x=>x.id!==t.id),users:prev.users.filter(u=>u.teacherId!==t.id),courses:prev.courses.map(c=>c.teacherId===t.id?{...c,teacherId:""}:c)}));
    toast("🗑 Teacher deleted.");
  }
 
  return(
    <div>
      {showModal&&(
        <Modal title="Create New Teacher Account" onClose={()=>setShowModal(false)}>
          <Field label="Full Name" required><input value={form.name} onChange={e=>setForm(f=>({...f,name:e.target.value}))} style={inp} placeholder="e.g. Jane Smith"/></Field>
          <Field label="Email (used for login)" required><input value={form.email} onChange={e=>setForm(f=>({...f,email:e.target.value}))} style={inp} placeholder="jsmith@school.edu"/></Field>
          <Field label="Password" required><input type="password" value={form.pass} onChange={e=>setForm(f=>({...f,pass:e.target.value}))} style={inp} placeholder="Set initial password"/></Field>
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
            <Field label="Room"><input value={form.room} onChange={e=>setForm(f=>({...f,room:e.target.value}))} style={inp}/></Field>
            <Field label="Subject"><input value={form.subject} onChange={e=>setForm(f=>({...f,subject:e.target.value}))} style={inp}/></Field>
          </div>
          {err&&<div style={{color:S.missing,background:"#fff0f0",borderRadius:3,padding:"6px",marginBottom:8,fontSize:12}}>⚠ {err}</div>}
          <div style={{display:"flex",gap:8,justifyContent:"flex-end",marginTop:8}}>
            <button onClick={()=>setShowModal(false)} style={{background:"#eee",borderRadius:3,padding:"7px 16px",fontSize:12}}>Cancel</button>
            <button onClick={submit} style={{background:"#8b0000",color:"#fff",borderRadius:3,padding:"7px 16px",fontSize:12,fontWeight:700}}>Create Teacher</button>
          </div>
        </Modal>
      )}
      <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
        <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",justifyContent:"space-between",alignItems:"center"}}>
          <span style={{fontWeight:700,fontSize:12}}>Teachers ({db.teachers.length})</span>
          <button onClick={()=>setShowModal(true)} style={{background:"#8b0000",color:"#fff",borderRadius:3,padding:"5px 14px",fontSize:11,fontWeight:700}}>+ Add Teacher</button>
        </div>
        <table><thead><tr style={{background:S.headerBg}}>{["Name","Email","Room","Subject","Courses","Action"].map(h=><th key={h} style={{padding:"6px 10px",color:"#fff",fontSize:11}}>{h}</th>)}</tr></thead>
          <tbody>{db.teachers.map((t,i)=>{const courses=db.courses.filter(c=>c.teacherId===t.id);return(<tr key={t.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
            <td style={{padding:"6px 10px",fontWeight:700,fontSize:12}}>{t.name}</td>
            <td style={{padding:"6px 10px",color:S.link,fontSize:12}}>{t.email}</td>
            <td style={{padding:"6px 10px"}}>{t.room}</td>
            <td style={{padding:"6px 10px"}}>{t.subject}</td>
            <td style={{padding:"6px 10px",fontSize:11,color:S.muted}}>{courses.map(c=>c.name).join(", ")||"None"}</td>
            <td style={{padding:"6px 8px"}}><button onClick={()=>del(t)} style={{background:"#ffebee",color:S.missing,border:`1px solid ${S.missing}44`,borderRadius:2,padding:"2px 8px",fontSize:11}}>Delete</button></td>
          </tr>);})}</tbody>
        </table>
      </div>
    </div>
  );
}
 
function AdminStudents({db,setDb,toast}){
  const [showModal,setShowModal]=useState(false);
  const [form,setForm]=useState({first:"",last:"",grade:"7",dob:"",email:"",pass:"",locker:"",bus:"",counselor:""});
  const [err,setErr]=useState("");
 
  function submit(){
    if(!form.first.trim()||!form.last.trim()||!form.email.trim()||!form.pass.trim()){setErr("First name, last name, email, and password are required.");return;}
    if(db.users.find(u=>u.email.toLowerCase()===form.email.toLowerCase())){setErr("Email already in use.");return;}
    const sId="s"+Date.now();const uId="u"+Date.now();
    const newSt={id:sId,first:form.first,last:form.last,grade:form.grade,dob:form.dob,email:form.email,locker:form.locker,bus:form.bus,counselor:form.counselor};
    const newU={id:uId,email:form.email,pass:form.pass,role:"student",name:form.first+" "+form.last,studentId:sId};
    setDb(prev=>({...prev,students:[...prev.students,newSt],users:[...prev.users,newU]}));
    toast("✅ Student '"+form.first+" "+form.last+"' created!");setShowModal(false);setErr("");
  }
 
  function del(s){
    if(!window.confirm(`Delete student "${s.first} ${s.last}"?`))return;
    setDb(prev=>({...prev,students:prev.students.filter(x=>x.id!==s.id),users:prev.users.filter(u=>u.studentId!==s.id),courses:prev.courses.map(c=>({...c,studentIds:c.studentIds.filter(id=>id!==s.id)}))}));
    toast("🗑 Student deleted.");
  }
 
  return(
    <div>
      {showModal&&(
        <Modal title="Add New Student" onClose={()=>setShowModal(false)} width={520}>
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
            <Field label="First Name" required><input value={form.first} onChange={e=>setForm(f=>({...f,first:e.target.value}))} style={inp}/></Field>
            <Field label="Last Name" required><input value={form.last} onChange={e=>setForm(f=>({...f,last:e.target.value}))} style={inp}/></Field>
          </div>
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
            <Field label="Grade"><select value={form.grade} onChange={e=>setForm(f=>({...f,grade:e.target.value}))} style={inp}>{["6","7","8"].map(g=><option key={g} value={g}>{g}th</option>)}</select></Field>
            <Field label="Date of Birth"><input type="date" value={form.dob} onChange={e=>setForm(f=>({...f,dob:e.target.value}))} style={inp}/></Field>
          </div>
          <Field label="Email (login)" required><input value={form.email} onChange={e=>setForm(f=>({...f,email:e.target.value}))} style={inp}/></Field>
          <Field label="Password" required><input type="password" value={form.pass} onChange={e=>setForm(f=>({...f,pass:e.target.value}))} style={inp}/></Field>
          <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
            <Field label="Locker"><input value={form.locker} onChange={e=>setForm(f=>({...f,locker:e.target.value}))} style={inp}/></Field>
            <Field label="Bus"><input value={form.bus} onChange={e=>setForm(f=>({...f,bus:e.target.value}))} style={inp}/></Field>
          </div>
          <Field label="Counselor"><input value={form.counselor} onChange={e=>setForm(f=>({...f,counselor:e.target.value}))} style={inp}/></Field>
          {err&&<div style={{color:S.missing,background:"#fff0f0",borderRadius:3,padding:"6px",marginBottom:8,fontSize:12}}>⚠ {err}</div>}
          <div style={{display:"flex",gap:8,justifyContent:"flex-end",marginTop:8}}>
            <button onClick={()=>setShowModal(false)} style={{background:"#eee",borderRadius:3,padding:"7px 16px",fontSize:12}}>Cancel</button>
            <button onClick={submit} style={{background:"#8b0000",color:"#fff",borderRadius:3,padding:"7px 16px",fontSize:12,fontWeight:700}}>Add Student</button>
          </div>
        </Modal>
      )}
      <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
        <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",display:"flex",justifyContent:"space-between",alignItems:"center"}}>
          <span style={{fontWeight:700,fontSize:12}}>Students ({db.students.length})</span>
          <button onClick={()=>setShowModal(true)} style={{background:"#8b0000",color:"#fff",borderRadius:3,padding:"5px 14px",fontSize:11,fontWeight:700}}>+ Add Student</button>
        </div>
        <table><thead><tr style={{background:S.headerBg}}>{["Name","Grade","Email","Locker","Bus","Counselor","Action"].map(h=><th key={h} style={{padding:"6px 10px",color:"#fff",fontSize:11}}>{h}</th>)}</tr></thead>
          <tbody>{db.students.map((s,i)=><tr key={s.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
            <td style={{padding:"6px 10px",fontWeight:700,fontSize:12}}>{s.last}, {s.first}</td>
            <td style={{padding:"6px 10px",textAlign:"center"}}>{s.grade}</td>
            <td style={{padding:"6px 10px",color:S.link,fontSize:11}}>{s.email}</td>
            <td style={{padding:"6px 10px",fontSize:11}}>{s.locker}</td>
            <td style={{padding:"6px 10px",fontSize:11}}>{s.bus}</td>
            <td style={{padding:"6px 10px",fontSize:11}}>{s.counselor}</td>
            <td style={{padding:"6px 8px"}}><button onClick={()=>del(s)} style={{background:"#ffebee",color:S.missing,border:`1px solid ${S.missing}44`,borderRadius:2,padding:"2px 8px",fontSize:11}}>Delete</button></td>
          </tr>)}</tbody>
        </table>
      </div>
    </div>
  );
}
 
function AdminUsers({db,setDb,toast}){
  return(
    <div style={{background:"#fff",border:`1px solid ${S.borderDark}`,borderRadius:3,overflow:"hidden"}}>
      <div style={{background:S.sectionHdr,borderBottom:`1px solid ${S.sectionBdr}`,padding:"7px 10px",fontWeight:700,fontSize:12}}>All User Accounts ({db.users.length})</div>
      <table><thead><tr style={{background:S.headerBg}}>{["Name","Email","Role","Linked ID"].map(h=><th key={h} style={{padding:"6px 10px",color:"#fff",fontSize:11}}>{h}</th>)}</tr></thead>
        <tbody>{db.users.map((u,i)=><tr key={u.id} style={{background:i%2===0?S.rowOdd:S.rowEven,borderBottom:`1px solid ${S.border}`}}>
          <td style={{padding:"6px 10px",fontWeight:700,fontSize:12}}>{u.name}</td>
          <td style={{padding:"6px 10px",color:S.link,fontSize:12}}>{u.email}</td>
          <td style={{padding:"6px 10px"}}><span style={{background:u.role==="admin"?"#b71c1c":u.role==="teacher"?S.navBg:S.gradeGreen,color:"#fff",borderRadius:3,padding:"2px 8px",fontSize:10,fontWeight:700,textTransform:"uppercase"}}>{u.role}</span></td>
          <td style={{padding:"6px 10px",fontFamily:"monospace",fontSize:11,color:S.muted}}>{u.teacherId||u.studentId||"—"}</td>
        </tr>)}</tbody>
      </table>
    </div>
  );
}
 
/* ─── PLACEHOLDER ───────────────────────────────────────────────── */
function Placeholder({t}){return<div style={{background:"#fff",border:`1px solid ${S.border}`,borderRadius:3,padding:24,color:S.muted,textAlign:"center",fontSize:13}}>{t}</div>;}
 
/* ══════════════════════════════════════════════════════════════════
   ROOT APP
══════════════════════════════════════════════════════════════════ */
export default function App(){
  const [db,setDb]=useState(initDB);
  const [session,setSession]=useState(null); // logged-in user object
 
  function login(user){setSession(user);}
  function logout(){setSession(null);}
 
  return(
    <>
      <style>{G}</style>
      {!session&&<Login db={db} onLogin={login}/>}
      {session?.role==="student"&&<StudentPortal user={session} db={db} setDb={setDb} onLogout={logout}/>}
      {session?.role==="teacher"&&<TeacherPortal user={session} db={db} setDb={setDb} onLogout={logout}/>}
      {session?.role==="admin"&&<AdminPortal user={session} db={db} setDb={setDb} onLogout={logout}/>}
    </>
  );
}
